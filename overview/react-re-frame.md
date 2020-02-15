# Re-frame

[re-frame](https://github.com/Day8/re-frame) is an application framework for creating more complex single page applications [SPAs] in ClojureScript, using [Reagent]() and [hiccup] style description for generating content.

![ClojureScript re-frame stack conceptual view](/images/clojurescript-reframe-stack-concept.png)

[![PurelyFunctional.tv Reframe Stack Overview](/images/purelyfunctional-tv-reframe-overview.png)](https://purelyfunctional.tv/lesson/re-frame-overview/)


## Why use re-frame?

1.  You are developing [Single Page Applications (SPA)] in ClojureScript, and you are looking for a framework and guidelines on how to organise the parts of that application effectively.

2.  `reactive programming`, `functional programming` and `immutable data` is the right approach for your application.


## Functional Model View Controller design

re-frame has Model, View, and Components in its design, created with pure functions (or pure data).  An application is wired together via reactive data flows.

To build a re-frame app, you:
 - design your app's data structure (data layer)
 - write and register subscription functions (query layer)
 - write Reagent component functions  (view layer)
 - write and register event handler functions  (control layer and/or state transition layer)




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
