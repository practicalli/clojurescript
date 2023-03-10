# Review Reagent Project

Lets look at the major parts of the code we have been given when we created the project from the `figwheel` template.

## Project Configuration - dependencies & plugins

Clojure, ClojureScript and reagent are the important dependencies in this project.  The `core.async` library is often used to avoid using callbacks in react-style applications, but we do not use `core.async` in this example.

```clojure
  :dependencies [[org.clojure/clojure "1.9.0-alpha17"]
                 [org.clojure/clojurescript "1.9.908"]
                 [org.clojure/core.async  "0.3.443"]
                 [reagent "0.7.0"]]
```

The `lein-figwheel` plugin provides all the nice features of figwheel, especially live reloading of code changes into the browser.

The `lein-cljsbuild` compiles the ClojureScript code into JavaScript.  There is an exclusion on this plugin to avoid pulling in a second dependency of Clojure (as we have explicitly defined it in the dependencies)

```clojure
  :plugins [[lein-figwheel "0.5.13"]
            [lein-cljsbuild "1.1.7" :exclusions [[org.clojure/clojure]]]]
```


## Web page

The web page is a very simple html page containing a `<div>` element with an id of `app`.  When we look at the react `render` in the ClojureScript code, we see that this id is used as a placeholder for our ClojureScript application.

```html
  <body>
    <div id="app">
      <h2>Figwheel template</h2>
      <p>Checkout your developer console.</p>
    </div>
    <script src="js/compiled/tictactoe_reagent.js" type="text/javascript"></script>
  </body>
```

## ClojureScript code

Include the reagent implementation of atom into the namespace.

The reagent atom is the same as the clojure atom in that it is a mutable container that manages state changes through software transactional memory.

The reagent atom (sometimes referred to as ratom) allows reagent to watch changes in the application state and update reagent components are affected by the state change.

```clojure
(ns tictactoe-reagent.core
    (:require [reagent.core :as reagent :refer [atom]]))
```

Enable printing out messages to the JavaScript console window from the ClojureScript code.

Using `enable-console-print!` sets *print-fn* to console.log, which makes logging to a browser’s console very simple.

```clojure

(enable-console-print!)

(println "This text is printed from src/tictactoe-reagent/core.cljs. Go ahead and edit it and see reloading in action.")
```

A common approach for react style applications is to define a name called `app-state` that uses an atom.

`defonce` is used over `def` so that the `app-state` is not reset each time you save a change in the ClojureScript file.

```clojure
;; define your app data so that it doesn't get over-written on reload

(defonce app-state (atom {:text "Hello world!"}))

```

The figwheel reagent project provides an example component called `hellow-world`

Components in reagent are simply Clojure functions.

```clojure
(defn hello-world []
  [:div
   [:h1 (:text @app-state)]
   [:h3 "Edit this and watch it change!"]])

```

Components are displayed in your application using the reagent `render` function.

The `render` function takes one or more components as an argument as well as a place on the page to render those components.

```clojure
(reagent/render-component [hello-world]
                          (. js/document (getElementById "app")))
```


The project also comes with a helper function that is called every time figwheel compiles a new saved change and pushes it to the JavaScript REPL.

You can force an update each time you save a change to the ClojureScript source code.  For example, the commented out `swap` function would increment a counter in the `app-state`

```clojure
(defn on-js-reload []
  ;; optionally touch your app-state to force rerendering depending on
  ;; your application
  ;; (swap! app-state update-in [:__figwheel_counter] inc)
)
```


> #### Hint:: Print board game state on every change
> The `on-js-reload` function can be used to print out the board game every time a change is made.
```clojure
(defn on-js-reload []
  (prn "Game board state:" (@app-state :board)))
```
