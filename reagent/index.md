# Reagent

[Reagent](https://reagent-project.github.io/) provides a ClojureScript interface to React.js, simplifying the development of single page apps and web user interfactes.  Reagent apps are very fast as immutable data structures makes calculating virtual dom changes extremely efficient.

React components are ClojureScript functions, state is held in ClojureScript data structures and the user interface can be generated using a [Hiccup-like syntax](hiccup-style-syntax.md).


> #### TODO::work in progress, sorry

## Designing a Reagent app
A simple reagent app consists of 3 main sections

* state - shared between one or more components
* components - behavior of the application, such as rendering content
* rendering - render components and update them when state changes


### State
The application state is modeled using Clojure data structures, e.g. hash-maps, vectors, contained within a reagent atom.

A reagent atom is a mutable container into which new values can be swapped or reset in a controlled way (Software Transactional Memory)

### Components are Clojure functions


```clojure
(defn hello []
  [:div "I am a reagent component, defining HTML content using the hiccup style syntax"])
```


### Rendering



<!-- It’s simply a function that returns a vector containing a keyword and a string. Nothing more than bread and butter Clojure. If you’re familiar with React, you might be wondering where createClass, componentDidMount, render and all of that other hoopla went. There’s no boilerplate at all! -->

<!-- React fans might be crying fowl about now. The above would be React.createElement('div', null, 'hello world') in React. Also pretty simple. But in Reagent, there is no distinction between elements and components, they’re all just vanilla ClojureScript functions. -->



* [Reagent Rocks tutorial](http://www.mattgreer.org/articles/reagent-rocks/#on-to-reagent)
