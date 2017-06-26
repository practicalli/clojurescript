Quantified Self Tool
Lets Get Started
Run these commands
Open your browser’s console.
Look for the printed message

lein new figwheel mememe  -- --reagent 
cd mememe
open . 
lein figwheel
open http://localhost:3449

1
2
3
4
5
6
lein new figwheel mememe  -- --reagent 
cd mememe
open . 
lein figwheel
open http://localhost:3449
 
index.html
Add bootstrap and container class



 
1
 
Figwheel template
Checkout your developer console.

 

core.clj

(defn hello-world []
  [:h1 "Hello World"])

(reagent/render-component [hello-world]
                          (. js/document (getElementById "app")))


1
2
3
4
5
6
7
(defn hello-world []
  [:h1 "Hello World"])
 
(reagent/render-component [hello-world]
                          (. js/document (getElementById "app")))
 
 
Add A button

  [:div
   [:h1 (:text @app-state)]
   [:button "Push Me"]]

1
2
3
4
  [:div
   [:h1 (:text @app-state)]
   [:button "Push Me"]]
 
Make it do something

   [:button {:on-click (fn [e] (println "I've been pushed"))} "Push Me"]

1
2
   [:button {:on-click (fn [e] (println "I've been pushed"))} "Push Me"]
 
Make the action visible

   [:button {:on-click #(swap! app-state assoc :text (str "It is now " (js/Date.)))}
            "Push Me"]

1
2
3
   [:button {:on-click #(swap! app-state assoc :text (str "It is now " (js/Date.)))}
            "Push Me"]
 
About Me
Developer for > ~20 years
Consultant (hire me)
Data intensive, (near) real time, distributed systems
Rich, reactive front ends
Love Clojure/ClojureScript and Elixir/Phoenix/Elm
Interested in embedded (Nerves)
@JulioBarros, E-String.com
ClojureScript (CLJS)
Clojure (lisp) that targets JavaScript
Interops well with JavaScript
Uses Google Closure compiler for optimization
Runs in the browser and on NodeJS
CLJSRN uses react native for native mobile apps
planck node based ClojureScript repl
Why ClojureScript
Simple language
Functional approach
Data is immutable by default
Data (value) oriented
Core Async concurrency management
Clojure(Script)
Parens are hugs for your code.

myThing.doSomething(parameter1,parameter2);

1
2
myThing.doSomething(parameter1,parameter2);
 

(do-something my-thing parameter1 parameter2)

1
2
(do-something my-thing parameter1 parameter2)
 
Dynamically Typed
Spec helps with type constraint/contract checks and generative testing
Also Plumatic Schema and many validation libraries

(s/def ::odd? (s/and integer? odd?))

(s/valid? ::odd? 3)
=&gt; true

(s/explain ::odd? 2)
=&gt; val: 2 fails spec: :spectest.core/odd? predicate: odd?

1
2
3
4
5
6
7
8
(s/def ::odd? (s/and integer? odd?))
 
(s/valid? ::odd? 3)
=&gt; true
 
(s/explain ::odd? 2)
=&gt; val: 2 fails spec: :spectest.core/odd? predicate: odd?
 
Lists
Parentheses (round braces) denote lists.
Lists are a sequence of things.
Usually the first item is executed.
quote or ’ keeps the list from being executed.

(function parameter1 parameter2)

1
2
(function parameter1 parameter2)
 

(+ 3 4) 
=&gt; 7

1
2
3
(+ 3 4) 
=&gt; 7
 

'(1 2 3) ;; [1 2 3] more common

1
2
'(1 2 3) ;; [1 2 3] more common
 
Vectors
Square brackets, [] denote a vector (array).
Can contain any and mixed types.

[1 2 3]
[1 2 [3 4]]

1
2
3
[1 2 3]
[1 2 [3 4]]
 

(count [5 5 5])
=&gt; 3

1
2
3
(count [5 5 5])
=&gt; 3
 

(get [1 2 3] 1) ;; Note: zero based.
=&gt; 2

1
2
3
(get [1 2 3] 1) ;; Note: zero based.
=&gt; 2
 

[3 {:name "Joe"} [1 2 3] '(1 2 [3 5])]

1
2
[3 {:name "Joe"} [1 2 3] '(1 2 [3 5])]
 
Maps
Called hash maps, hash or dictionary in other languages.
Maps associate keys and values.
Denoted by curly braces {} commas optional.
Anything can be a key.

;; a map or record for a person
{:first-name "Julio"
 :last-name "Barros"
 "age" 29
 42 "The Answer"}

1
2
3
4
5
6
;; a map or record for a person
{:first-name "Julio"
 :last-name "Barros"
 "age" 29
 42 "The Answer"}
 
Getting values from a map

(def m {:y "because"}) ;; binds a value to the symbol 'm'

(get m :y) ;; gets the value of y. Compare to m.get("y")
=&gt; "because"

(:y m) ;; same thing just shorter

(m :y) ;; this works too

1
2
3
4
5
6
7
8
9
(def m {:y "because"}) ;; binds a value to the symbol 'm'
 
(get m :y) ;; gets the value of y. Compare to m.get("y")
=&gt; "because"
 
(:y m) ;; same thing just shorter
 
(m :y) ;; this works too
 
assoc
Associates (adds or updates) a key and value in one map creating a new map.


(assoc {:name "Julio" } :loves "Clojure")

;; results in - ie outputs 

{:name "Julio" :loves "Clojure"}

(def m {:x 5})
(assoc m :y 3) =&gt; {:x 5, :y 3}
=&gt; {:x 5, :y 3}
m 
=&gt; {:x 5}

1
2
3
4
5
6
7
8
9
10
11
12
(assoc {:name "Julio" } :loves "Clojure")
 
;; results in - ie outputs 
 
{:name "Julio" :loves "Clojure"}
 
(def m {:x 5})
(assoc m :y 3) =&gt; {:x 5, :y 3}
=&gt; {:x 5, :y 3}
m 
=&gt; {:x 5}
 
Interesting types


“I’m a string” ;; strings
:name ;; keyword
meaning-of-life ;; symbol

3 ;; integer
3.0 ;; double Note: 3.0 is different than “3.0”

{} ;; map
[] ;; vectors
() ;; lists
#{} ;; set - unordered collection with no duplicates

;; collections can contain other collections and functions
{:name “Julio”
:tags #{“Portland” “Programmer”}
:pets [{:name “Rex” :type “dog”}]
:strategy (fn [x] ….)
}

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
 
“I’m a string” ;; strings
:name ;; keyword
meaning-of-life ;; symbol
 
3 ;; integer
3.0 ;; double Note: 3.0 is different than “3.0”
 
{} ;; map
[] ;; vectors
() ;; lists
#{} ;; set - unordered collection with no duplicates
 
;; collections can contain other collections and functions
{:name “Julio”
:tags #{“Portland” “Programmer”}
:pets [{:name “Rex” :type “dog”}]
:strategy (fn [x] ….)
}
 
Functions
Takes zero or more input parameters and returns a single value.

The return value could be a list or map or vectors of multiple things.

Returns the result of the last expression executed.


(defn my-function-name
  "A documentation string"
  [param1 param2]
  (functionA param1 param2))

(defn increment
  "Adds one to the parameter"
  [a-number]
  (+ 1 a-number))

(increment 3)

;; (defn x [] ...) same as (def x (fn [] ...))

(def twotimes (fn [x] (* 2 x)))
(def triple #(* 3 %))
(triple 5)

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
(defn my-function-name
  "A documentation string"
  [param1 param2]
  (functionA param1 param2))
 
(defn increment
  "Adds one to the parameter"
  [a-number]
  (+ 1 a-number))
 
(increment 3)
 
;; (defn x [] ...) same as (def x (fn [] ...))
 
(def twotimes (fn [x] (* 2 x)))
(def triple #(* 3 %))
(triple 5)
 
Pure Functions
Don’t modify state – no side effects
Always return same value for same input

(inc 3) ;; pure
(rand) ;; impure

1
2
3
(inc 3) ;; pure
(rand) ;; impure
 
Make as many functions as possible pure.
Functional Functions
map – apply a function to every item in a sequence returning a sequence

(map twotimes [1 2 3])
=> (2 4 6)
reduce – apply a function to every item (along with an accumulator value) returning one thing. foldl

(defn add-square [acc n] (+ acc (* n n)))
(reduce add-square 0 [1 2 3])
=> 14
apply – call a function with the item in a sequence as parameters

(apply + [1 2 3]) ;; same as (+ 1 2 3)
=> 6
(apply + (range 11))
=> 55
Common fun cont.
filter / remove – keep or remove items that match a predicate

(filter even? (range 10))
=> (0 2 4 6 8)
(remove even? (range 10))
=> (1 3 5 7 9)
Extra credit: What is the sum of all the even numbers from 1 to 100.
assoc / dissoc – add or remove item from collection

(assoc {:a 1} :b 2)
=> {:a 1, :b 2}
(dissoc {:a 1 :b 2} :b )
=> {:a 1}
Common fun cont2.
assoc-in – updates a nested value with a value

(def m {:name "Julio" :age 29})
(assoc-in m [:age] 30)
=> {:name "Julio", :age 30}
update-in – updates a nested value with a function

(update-in m [:age] inc)
{:name "Julio", :age 30}
Anonymous function shorthand
#() – useful for simple inline functions

(map #(* % %) (range 10))
=> (0 1 4 9 16 25 36 49 64 81)
How do you get the sum of the squares of a list of numbers

(apply + (map #(* % %) (range 10)))
=> 285
Immutability and Binding
Data is immutable but you can bind and re-bind ‘variable’ names (symbols).


(defn myfun []
  (let [x 3
        y x
        x 5]
    (println x y)))

=&gt; 5 3

(defn myfun2 []
  (let [x ["joe" "bob"]
        y x
        x (conj x "jane")]
    (println x y)))
    
=&gt; [joe bob jane] [joe bob]


1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
(defn myfun []
  (let [x 3
        y x
        x 5]
    (println x y)))
 
=&gt; 5 3
 
(defn myfun2 []
  (let [x ["joe" "bob"]
        y x
        x (conj x "jane")]
    (println x y)))
    
=&gt; [joe bob jane] [joe bob]
 
 
Atoms
Managed shared, synchronous state. Think of it like an in memory db.

Created with function atom.

Derefrence it with deref or @.

Change it with reset! or swap!.


(def a (atom "Hello World"))
a = #atom["Hello World" 0x4887b548]
@a =&gt; "Hello World"

(reset! a "Goodbye")
(swap! a clojure.string/upper-case)
@a =&gt; "GOODBYE"

1
2
3
4
5
6
7
8
(def a (atom "Hello World"))
a = #atom["Hello World" 0x4887b548]
@a =&gt; "Hello World"
 
(reset! a "Goodbye")
(swap! a clojure.string/upper-case)
@a =&gt; "GOODBYE"
 

(def app-data (atom {:customers {...}
                     :todo-items [...]
                     :account-info {...}}))
    

1
2
3
4
5
(def app-data (atom {:customers {...}
                     :todo-items [...]
                     :account-info {...}}))
    
 
Using ClojureScript
Direct DOM Manipulation
A la jQuery
Dommy
Domina

$('#my-button).click(function() {...});

1
2
$('#my-button).click(function() {...});
 

(.getElementById js/document "my-button")

(dommy/listen! (sel1 :#my-button) :click click-handler)

(dommy/append! (sel1 :#todos) todo-element)

1
2
3
4
5
6
(.getElementById js/document "my-button")
 
(dommy/listen! (sel1 :#my-button) :click click-handler)
 
(dommy/append! (sel1 :#todos) todo-element)
 
ReactJS
A Javascript library for building user interfaces.

Creates a JS based (virtual) DOM and manages updating the browsers DOM.

Clojure options to wrap ReactJS:

OM(Next)
Reagent
Quiescent
Keechma
Petrol
Rum
Reagent
Minimalistic and Clojure-esque.

Uses Hiccup syntax.

You write functions that return a vector of vectors (data).
Reagent changes vectors to React components/objects.
React uses those objects to update DOM.

(defn footer-component []
   [:p "Brought to you by the letter Q."])

(defn simple-component []
  [:div
   [:p "I am a component!"]
   [:button {:on-click my-click-handler} "Push me"]
   [:p.someclass "I have some class"]
   [footer-component]])

1
2
3
4
5
6
7
8
9
10
(defn footer-component []
   [:p "Brought to you by the letter Q."])
 
(defn simple-component []
  [:div
   [:p "I am a component!"]
   [:button {:on-click my-click-handler} "Push me"]
   [:p.someclass "I have some class"]
   [footer-component]])
 
Tooling
Leiningen or Boot
FigWheel
Bruce Hauman – Developing ClojureScript With Figwheel (video)
Templates to set up a project
lein or boot
Dependencies
Compilation
Running tests
Packaging
Deployment
FigWheel
Figwheel builds your ClojureScript code and hot loads it into the browser as you are coding!

Runs its own server to load assets
Watches and compiles your files
Gives you improved error messages
Pushes changes to the browser
Sets up a repl into your browser
Can co-exist with your regular server in development
Templates
Figwheel template
Chestnut template
Luminus Web “framework”
Lots of templates for your favorite libraries
Quantified Self Tracker

(defonce app-state (atom
                    {:counters {1 {:id 1 :name "Drink Water" :count 0}
                                2 {:id 2 :name "Stand up and stretch" :count 0}}}))

(defn increment-counter [c]
  (swap! app-state update-in [:counters (:id c) :count] inc))

(defn counter-view [c]
  [:div.row
      [:div.col-sm-1 (str (:count c))]
      [:div.col-sm-10 (:name c)]
   [:div.col-sm-1 
    [:button.btn.btn-default {:on-click #(increment-counter c)}  "Done It!"]]])

(defn hello-world []
  [:div
   [:h1 "Me Me Me!"]
   (for [c (vals (:counters @app-state))]
     ^{:key (:id c)}
     [counter-view c])])
     

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
(defonce app-state (atom
                    {:counters {1 {:id 1 :name "Drink Water" :count 0}
                                2 {:id 2 :name "Stand up and stretch" :count 0}}}))
 
(defn increment-counter [c]
  (swap! app-state update-in [:counters (:id c) :count] inc))
 
(defn counter-view [c]
  [:div.row
      [:div.col-sm-1 (str (:count c))]
      [:div.col-sm-10 (:name c)]
   [:div.col-sm-1 
    [:button.btn.btn-default {:on-click #(increment-counter c)}  "Done It!"]]])
 
(defn hello-world []
  [:div
   [:h1 "Me Me Me!"]
   (for [c (vals (:counters @app-state))]
     ^{:key (:id c)}
     [counter-view c])])
     
 
Add A Counter

(defn add-counter [text]
  (let [next-id (inc (count (keys (:counters @app-state))))
        new-counter {:id next-id :name text :count 0}]
    (swap! app-state update-in [:counters] assoc next-id new-counter)))
        
    
(defn new-counter []
  (let [text (atom "")]
    (fn []
      [:div.row
       [:div.col-sm-10
        [:input.form-control {:type "text" :value @text
                              :on-change #(reset! text (-&gt; % .-target .-value))}]]
       [:button.btn.btn-success {:on-click #(add-counter @text)} "Add"]])))
       
(defn hello-world []
  [:div
   [:h1 "Me Me Me!"]
   [new-counter]
   (for [c (vals (:counters @app-state))]
     ^{:key (:id c)}
     [counter-view c])])


1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
(defn add-counter [text]
  (let [next-id (inc (count (keys (:counters @app-state))))
        new-counter {:id next-id :name text :count 0}]
    (swap! app-state update-in [:counters] assoc next-id new-counter)))
        
    
(defn new-counter []
  (let [text (atom "")]
    (fn []
      [:div.row
       [:div.col-sm-10
        [:input.form-control {:type "text" :value @text
                              :on-change #(reset! text (-&gt; % .-target .-value))}]]
       [:button.btn.btn-success {:on-click #(add-counter @text)} "Add"]])))
       
(defn hello-world []
  [:div
   [:h1 "Me Me Me!"]
   [new-counter]
   (for [c (vals (:counters @app-state))]
     ^{:key (:id c)}
     [counter-view c])])
 
