# ClojureScript code

I have taken examples from a number of sources to give you a basic introduction to using Clojurescript.  Please see [Clojurescript Unraveled](http://funcool.github.io/clojurescript-unraveled) for a more complete reference guide

* Rafel Spacjer's blog: [Clojurescript: Javascript interop](http://www.spacjer.com/blog/2014/09/12/clojurescript-javascript-interop/)

## Defining scope


## Javascript scope included

ClojureScript defines special js namespace to allow accessing JavaScript types/functions/methods/objects defined in global scope (i.e. window object for browser).


```clojure
(def text js/globalName) ;; JS output: namespace.text = globalName;
```

Creating objects

We can create JavaScript objects from ClojureScript by adding . to the end of constructor function:

(def t1 (js/MyType.)) ;; JS output: namespace.t1 = new MyType;

(note: at first I thought that this generated JS code was wrong, because of the lack of parentheses, but as it clarifies it’s valid - if constructor function doesn’t have arguments, then parentheses can be skipped)

with arguments:

(def t2 (js/MyComplexType. "Bob")) ;; JS output: namespace.t2 = new MyComplexType("Bob");

There is also a different way of creating objects, by using the new function (the name of JS constructor function should be without period):

(def my-type (new js/MyComplexType "Bob")) ;; JS output: namespace.my_type = new MyComplexType("Bob");

Invoking methods

To invoke a JavaScript method we need to prefix the name of the method with the . (dot):

(.hello js/window) ;; JS output: window.hello();

which is a syntactic sugar of:

(. js/window (hello))

To pass arguments to the function we do:

(.helloAgain js/window "John") ;; JS output: window.helloAgain("John");

or

(. js/window (helloAgain "John"))

Same thing can be done with created object:

(def my-type (js/MyComplexType. "Bob")) ;; JS output: namespace.my_type = new MyComplexType("Bob");
(.hello my-type)                        ;; JS output: namespace.my_type.hello();

Accessing properties

ClojureScript provides a few ways of working with JavaScript properties. The simplest one is to use .- property access syntax:

(def my-type (js/MyType.))  ;; JS output: namespace.my_type = new MyType;
(def name (.-name my-type)) ;; JS output: namespace.name = namespace.my_type.name;

similar thing can be achieved by aget function, which takes object and the name of the property (as a string) as arguments:

(def name (aget my-type "name")) ;; JS output: namespace.name = namespace.my_type["name"];

The aget allows also accessing nested properties:

(aget js/object "prop1" "prop2" "prop3") ;; JS output: object["prop1"]["prop2"]["prop3"];

the same thing (generated code is different) can be done by using .. syntax:

(.. js/object -prop1 -prop2 -prop3) ;; JS output: object.prop1.prop2.prop3;

You can also set a value of a property from the ClojureScript, to do this you can use aset or set! functions:

The aset function takes name of the property as a string:

(def my-type (js/MyType.))
(aset my-type "name" "Bob") ;; JS output: namespace.my_type["name"] = "Bob";

and the set! takes a property access:

(set! (.-name my-type) "Andy") ;; JS output: namespace.my_type.name = "Andy";

Arrays

The aget function can be also used for accessing JavaScript array element:

(aget js/globalArray 1) ;; JS output: globalArray[1];

or if you want to get nested element you can use it in this way:

(aget js/globalArray 3 1) ;; JS output: globalArray[3][1];

Nested scopes

This subject was a bit confusing for me. In my project I wanted to translate such a code:

var map = new Microsoft.Maps.Map();

to ClojureScript. As you can see the Map function is in nested scope. The idiomatic way of accessing nested properties is to use .. or aget functions but this can’t be done for constructor function. In such case, we need to use the dot notation (even it’s not idiomatic for Clojure code):

(def m2 (js/Microsoft.Maps.Themes.BingTheme.))

or with the new function:

(def m1 (new js/Microsoft.Maps.Themes.BingTheme))

If we write this expression like this:

(def m3 (new (.. js/Microsoft -Maps -Themes -BingTheme)))

we will get an exception:

First arg to new must be a symbol at line
                core.clj:4403 clojure.core/ex-info
             analyzer.clj:268 cljs.analyzer/error
             analyzer.clj:265 cljs.analyzer/error
             analyzer.clj:908 cljs.analyzer/eval1316[fn]
             MultiFn.java:241 clojure.lang.MultiFn.invoke
            analyzer.clj:1444 cljs.analyzer/analyze-seq
            analyzer.clj:1532 cljs.analyzer/analyze[fn]
            analyzer.clj:1525 cljs.analyzer/analyze
             analyzer.clj:609 cljs.analyzer/eval1188[fn]
             analyzer.clj:608 cljs.analyzer/eval1188[fn]
             MultiFn.java:241 clojure.lang.MultiFn.invoke
            analyzer.clj:1444 cljs.analyzer/analyze-seq
            analyzer.clj:1532 cljs.analyzer/analyze[fn]
            analyzer.clj:1525 cljs.analyzer/analyze
            analyzer.clj:1520 cljs.analyzer/analyze
             compiler.clj:908 cljs.compiler/compile-file*
            compiler.clj:1022 cljs.compiler/compile-file

Creating JavaScript objects

There are many cases where we need to pass JavaScript object to a method from ClojureScript. In general ClojureScript works with its own data structures (immutable, persistent vector, map, set etc.) that can be converted to plain JS objects. There are several ways of doing it.

If we want to create a simple JavaScript object from the list of key value pairs we can use js-obj macro:

(def my-object (js-obj "a" 1 "b" true "c" nil)) ;; JS output: namespace.my_object_4 = (function (){var obj6284 = {"a":(1),"b":true,"c":null};return obj6284;

Note that js-obj forces you to use strings as keys and basic data literals (string, number, boolean) as values. The ClojureScript data structures won’t be changed, so this:

(def js-object (js-obj  :a 1 :b [1 2 3] :c #{"d" true :e nil}))

will create such JavaScript object:

{
  ":c" cljs.core.PersistentHashSet, 
  ":b" cljs.core.PersistentVector, 
  ":a" 1
}

as you can see there are used internal types such as:
cljs.core.PersistentHashSet
cljs.core.PersistentVector
and the ClojureScript keyword was changed to string prefixed with colon.

To solve this problem we can use clj->js function that:
“Recursively transforms ClojureScript values to JavaScript.
sets/vectors/lists become Arrays, Keywords and Symbol become Strings,
Maps become Objects.”

(def js-object (clj->js  :a 1 :b [1 2 3] :c #{"d" true :e nil}))

will produce such object:

{
  "a": 1,
  "b": [1, 2, 3],
  "c": [null, "d", "e", true]
}

There is also one more way of producing JavaScript objects - we can use #js reader literal:

(def js-object #js {:a 1 :b 2})

which generates code:

namespace.core.js_object = {"b": (2), "a": (1)};

When working with #js you need to be cautious, because this literal also won’t transform inner structures (it’s shallow):

(def js-object #js {:a 1 :b [1 2 3] :c {"d" true :e nil}})

will create such object:

{
  "c": cljs.core.PersistentArrayMap, 
  "b": cljs.core.PersistentVector, 
  "a": 1
}

to solve this you need to add #js before every ClojureScript structure:

(def js-object #js {:a 1 :b #js [1 2 3] :c #js ["d" true :e nil]})

JavaScript object:

{
  "c": {
    "e": null,
    "d": true
  },
  "b": [1, 2, 3 ],
  "a": 1
}

Using JavaScript objects

There are situations when we need to convert JavaScript object or array into ClojureScript data structure. We can do this by using js->clj function that:
"Recursively transforms JavaScript arrays into ClojureScript vectors, and JavaScript objects into ClojureScript maps. With
option ‘:keywordize-keys true’ will convert object fields from
strings to keywords.

(def my-array (js->clj (.-globalArray js/window)))
(def first-item (get my-array 0)) ;; 1

(def my-obj (js->clj (.-globalObject js/window)))
(def a (get my-obj "a")) ;; 1

as the function doc states we can use :keywordize-keys true to convert string keys of created map to keywords:

(def my-obj-2 (js->clj (.-globalObject js/window) :keywordize-keys true))
(def a-2 (:a my-obj-2)) ;; 1

Addition

If all other methods of working with JavaScript failed, there is a js* that takes a string as an argument and emits it as a JavaScript code:

(js* "alert('my special JS code')") ;; JS output: alert('my special JS code');

Exposing ClojureScript functions

It is worth noting that the exact form of JavaScript code generated from ClojureScript depends on compiler settings. Those settings can be defined in Leiningen project.clj file:

Part of project.clj file:

:cljsbuild {
    :builds [{:id "dev"
              :source-paths ["src"]
              :compiler {
                :main your-namespace.core
                :output-to "out/your-namespace.js"
                :output-dir "out"
                :optimizations :none
                :cache-analysis true
                :source-map true}}
             {:id "release"
              :source-paths ["src"]
              :compiler {
                :main blog-sc-testing.core
                :output-to "out-adv/your-namespace.min.js"
                :output-dir "out-adv"
                :optimizations :advanced
                :pretty-print false}}]}

As you can see above, there are two defined builds: dev and release. Please note the :optimizations parameter - for :advanced value the code will be truncated (not used code is removed) and renamed (shorter names are used).

For example, this ClojureScript code:

(defn add-numbers [a b]
  (+ a b))

will be compiled to such JavaScript code in :advanced mode:

function yg(a,b){return a+b}

The function name is completely “random”, so you can’t use it from JavaScript file. To be able to use defined in ClojureScript functions (with their original names) you should mark them with the :export metadata:

(defn ^:export add-numbers [a b]
  (+ a b))

The :export keyword tells compiler to export given function name to the outside world. (This is done by exportSymbol function from Google Closure Compiler - but I won’t go into the details). Then in your external JavaScript code you can invoke this function:

your_namespace.core.add_numbers(1,2);

Please, notice that all dashes were replaced by underscors.
Using external JavaScript libraries

The :advanced mode affects also invocation of the external libreries, because all functions/methods names are changed to minimal form. Lets take a ClojureScript code, that invokes PolarArea function form the Chart object:

(defn ^:export creat-chart []
  (let [ch (js/Chart.)]
    (. ch (PolarArea []))))

after compilation this code will look similar to this one:

function(){return(new Chart).Bc(zc)}

As you can see, the PolarArea method was changed to Bc name, which of course will cause runtime error. To prevent this, we need to tell compiler which names shouldn’t be changed. Those names should be defined in external JavaScript file (i.e. externs.js) and provided to the compiler. For our example the externs.js file should look like this one:

var Chart = {};
Chart.PolarArea = function() {};

The compiler should be informed about this file by :externs setting in project.clj file:

{:id "release"
              :source-paths ["src"]
              :compiler {
                         :main blog-sc-testing.core
                         :output-to "out-adv/your-namespace.min.js"
                         :output-dir "out-adv"
                         :optimizations :advanced
                         :externs ["externs.js"]
                         :pretty-print false}}

If we do all those things, created JavaScript code will contain correct invocation of PolarArea function:

function(){return(new Chart).PolarArea(Ec)}

To get more details about using external JavaScript libraries in ClojureScript I recommend you to read excellent blog post by Luke VanderHart about this.



# Interop

(. js/document (getElementById "app"))

(.-value input)


## core.async - communicating sequential processes

* processes
* channels
* coordination

using core.async allows you to write sequential logic that avoids the need for callback hell of hand-crafting asyncronous coding.

;; sudo code
(str "do something")
(send-to-channel)
(str "keep doing something")

;; put something on the channel
(put!)
(>!)

;; get something from the channel
(take!)
(<!)

;; go
(go
  (println "Waiting...")
  (<! events)
  (show! "Got an event"))

