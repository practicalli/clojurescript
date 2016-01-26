# Re-frame

[re-frame](https://github.com/Day8/re-frame) is a pattern for writing [SPAs] in ClojureScript, using [Reagent].

This repo contains both a **description of this pattern** and a **reference implementation**.

To quote McCoy: "It's MVC, Jim, but not as we know it".

re-frame does have M, V, and C parts but they aren't objects, they are pure functions (or pure data), and they are wired together via reactive data flows. It is sufficiently different in nature from traditional MVC that calling it MVC would be confusing

To build a re-frame app, you:
 - design your app's data structure (data layer)
 - write and register subscription functions (query layer)
 - write Reagent component functions  (view layer)
 - write and register event handler functions  (control layer and/or state transition layer)


## Why Should You Care About re-frame?

Either:

1.  You want to develop an [SPA] in ClojureScript, and you are looking for a framework; or
2.  You believe that, by early 2015, ReactJS had won the JavaScript framework wars and
    you are curious about the bigger implications. Is the combination of
    `reactive programming`, `functional programming` and `immutable data` going to
    **completely change everything**?  And, if so, what would that look like in a language
    that embraces those paradigms?

## Tutorials

* [TODO MVC app](https://github.com/Day8/re-frame/tree/master/examples/todomvc)
* [Phonecat port](https://dhruvp.github.io/2015/03/07/re-frame/)

## Features

1. The functions you write are pure, so the computational pieces of your app can
   be described, understood and tested independently.
   You won't need sophisticated Dependency Injection to test. So much
   incidental complexity evaporates.
2. These computational parts are composed via reactive data flows - a dynamic,
   unidirectional Signal graph.
3. The resulting architecture involves "derived data" flowing in a two-stage, reactive loop.
   Without realising it, you will be explicitly modelling time.
4. It is fast, straight out of the box. You won't have to go through [this sort of pain](http://blog.scalyr.com/2013/10/angularjs-1200ms-to-35ms/).
5. The surprising thing about re-frame is how simple it is. Beautifully simple! Our reference
   implementation is little more than 200 lines of (ClojureScript) code. Learn it in an afternoon.
6. But it scales up nicely to more complex apps.  Frameworks are just pesky overhead at small
   scale - measure them instead by how they help you tame the complexity of bigger apps.
7. Re-frame is impressively buzzword compliant: it has FRP-nature,
   unidirectional data flow, pristinely pure functions, conveyor belts, statechart-friendliness (FSM)
   and claims an immaculate hammock conception.
   It also has a charming xkcd reference (soon)
   and a hilarious, insiders-joke T-shirt, ideal for conferences (in design).
   What could possibly go wrong?

