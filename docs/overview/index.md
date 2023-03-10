# ClojureScript Overview 

>**Hint**  I love ClojureScript because its powerful, flexible and fast way of developing client-side or native mobile application

## ClojureScript is

* a **general purpose language** that compiles to JavaScript and runs in a Browser, on NodeJS, or Java Nashorn JavaScript engines
* a **functional programming language** with a data centric approach (mostly pure) 
* a **very small syntax** (12 primitives, 4 of which were added for Java interoperability)
* a **dynamic language** in terms of type inference and runtime (REPL)
* a **fast-feedback** approach for development, helping you quickly explore a problem domain
* a modern implementation of **LISP**
* a highly extensible language via **macros**
* an efficient way to manage state changes via **persistent data structures** & **software transactional memory**
* blessed with an amazing collection of libraries to solve modern programming challenges 

> **Hint** In functional programming we avoid changing state as much as possible.  If a function does not change state it is referentially transparent, always returning the same result when given the same input (arguments).  These are refered to as Pure Functions.  Pure functions are truely modular as they do not affect any other part of the system and do not require complex threading for scalability.


## Clojure & ClojureScript

[ClojureScript](https://github.com/clojure/clojurescript) is Clojure that compiles to to JavaScript and runs in the browser (JavaScript Engine).  Most of the code and libraries available for Clojure works seamlessly when compiled to JavaScript.

ClojureScript contains a compiler for Clojure that targets JavaScript. It is designed to emit JavaScript code which is compatible with the advanced compilation mode of the Google Closure optimizing compiler.

ClojureScript has recently had a strong focus on Reactive client side apps and mobile apps with Reactive Native.  Due to its immutable data structures, ClojureScript has been shown to outperform Facebook React, so much so that Facebook are now adding Immutable.js to their React framework to catch up.

There is a common file extension, `.cljc` that signifies code that is written to run on both the JVM and any JavaScript engine.


## Clojure & ClojureScript Community 

There is a vibrant and highly active community around Clojure & Clojurescript.  In London alone there is a regular monthly talk and 4 coding dojo every month run by the [London Clojurians](http://londonclojurians.org/)

## Community resources

[Clojure. tv](https://www.youtube.com/channel/UCaLlzGqiPE2QRj6sSOawJRg) and [Planet Clojure](http://planet.clojure.in/) are the tip of the iceburg to a large amount of Clojure resources available via the Internet.
