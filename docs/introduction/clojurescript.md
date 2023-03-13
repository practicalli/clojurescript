# ClojureScript Overview

[ClojureScript](https://clojurescript.org/reference/documentation){target=_blank} is an implementation of the [Clojure programming language](https://clojurescript.org/reference/documentation){target=_blank} for the JavaScript platform (JavaScript browsers and node.js)

The main difference of course between Clojure & ClojureScript is the host (Java or JavaScript) and the type of applications & services built with each language.

ClojureScript is predominately used for front-end applications, although can also be used as full stack solutions.

??? INFO "Minor Language differences"
    Due to limitations of the host JavaScript platform, some language features of Clojure are not available in ClojureScipt

    [:fontawesome-solid-book: ClojureScipt differences from Clojure](https://www.clojurescript.org/about/differences){target=_blank .md-button}



## Learning ClojureScipt

As Clojure & ClojureScript language are almost identical, any good Clojure book or exercises can also help to learn ClojureScript

[ClojureScript language reference](https://clojurescript.org/reference/documentation){target=_blank .md-button}

[ClojureScript unraveled](http://funcool.github.io/clojurescript-unraveled/){target=_blank .md-button}

[Practicalli Clojure Coding Challenges](https://practical.li/clojure/coding-challenges/){target=_blank .md-button}



## Development Tools

There are many [Clojure aware Editors](https://practical.li/clojure/clojure-editors/) available, use an editor most familiar with to minimize the initial learning requriements.

Clojure aware editors have the same core functionality, so initial choice is not that important.  As additional features become more important, then a review of editor tooling can be done with more insight.


## Build Automation

ClojureScript is trans-piled into JavaScript before running in a JavaScript browser engine or on node.js.

The main tools to support this workflow:

* Figwheel - ClojureScript focused with the ability to bundle JavaScript npm packages (typically the simplest approach)
* Shadow-cljs - implmentation of ClojureScipt for node.js and therefore deeply integrated into the npm infrastructure (initially more complex but potential simpler if managing a large amount of npm packages and dependencies)


### Fighweel

[Figwheel](https://figwheel.org/) is a simple approach and doesn't require node.js. ClojureScript applications can be built without JavaScript.  Figwheel does enabled use of npm packages via bundle though, should JavaScript packages be valuable to add.

[figwheel-template](https://github.com/bhauman/figwheel-template){target=_blank} creates ClojureScript projects with figwheel configuration and optionally react, reagent, rum and bundle (webpack) options.

[Figwheel](https://figwheel.org/){target=_blank .md-button}
[Figwheel Template](https://github.com/bhauman/figwheel-template){target=_blank .md-button}

??? INFO "Figwheel-main is library to use for Figwheel"
    Fighweel-main has replaced the figwheel library (now considered deprecated) and is a large rewrite of the tooling, providing a greatly enhanced experience.


### Shadow-cljs

Shadow-cljs is effectively built on top of node.js and therefore more integrated.  Assumes that node.js is well understood and significant use of JavaScript npm packages will be used

Read the user guide in detail to avoid common issues when starting

[Shadow-cljs User Guide](https://shadow-cljs.github.io/docs/UsersGuide.html){target=_blank .md-button}


## Common Libraries

As with any language, there are a wide range of choice for libraries to help build apps and many types of apps that can be built (UI / full-stacl / backend).

[reagent](https://reagent-project.github.io/) is the most commonly used ClojureScript library for front-end apps, especially single page applications.  reagent takes a react.js like approach.

[re-frame](http://day8.github.io/re-frame/) builds upon reagent and supports the building of more complex UIs and stateful workflows.


[reagent](https://reagent-project.github.io/){target=_blank .md-button}
[reframe](http://day8.github.io/re-frame/){target=_blank .md-button}
[rum](https://github.com/tonsky/rum){target=_blank .md-button}
