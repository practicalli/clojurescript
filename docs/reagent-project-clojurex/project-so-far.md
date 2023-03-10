# React ClojureX project so far

Thanks to the chestnut template our project already has some code that runs, so lets review what it does.

## Defining the namespace

Clojurescript uses namespaces to separate your application into logical areas.  The namespace matches the directory strucuture and filename.

So the `conference-reagent.core` namespace is defined in a file `src/cljs/conference-reagent/core.cljs`

As we are using functions from the reagent library, we include that library using the alias `reagent`.  Using `:refer` we replace the clojurescript atom with the reagent atom.

```clojure
(ns conference-reagent.core
  (:require [reagent.core :as reagent :refer [atom]]))
```

## Show information in the browser

Show the log and error messages in the browser console.

```clojure

(enable-console-print!)
```

## Defining the App State

We want to have a model of our data that we can track when it changes.  This is managed in our `app-state`.

The inital `app-state` is a map (hash map) that is an immutable data structure.  To manage changes to our state we wrap the `app-state` map with an atom.

An atom is a mutable container.  As the clojurescript atom has been replaced by the reagent atom, then reagent can track any changes to the contents and decide when to update components based on that change.

```clojure

(defonce app-state (atom {:text "Hello Chestnut!"}))
```

## A reagent component

The `greeting` function uses a [hiccup](https://github.com/weavejester/hiccup) like syntax to generate HTML from simple Clojure data structures.

In this example a `h1` heading is generated which contains the value pointed to by the key called `:text` from our `app-state` map.

```clojure
(defn greeting []
  [:h1 (:text @app-state)])
```

## Reagent render

The `reagent/render` function is used to display the components on screen.

The components to render are passed as a vector (array) to the render function, this allows reagent to control when a component is rendered (and re-rendered due to a change of state).

The components are rendered to a placeholder in the `resources/public/index.html` file, which contains a div with the class name `app`.

```clojure
(reagent/render [greeting] (js/document.getElementById "app"))
```

> #### Hint
> Our application is going to render a single component which defines the overall single page app.  That component will contain a number of child components.
>
> To render multiple components seperately, simply define more placeholder class names in the html file.
