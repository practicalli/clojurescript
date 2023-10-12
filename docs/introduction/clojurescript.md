# ClojureScript Overview

[ClojureScript](https://clojurescript.org/reference/documentation){target=_blank} is an implementation of the [Clojure programming language](https://clojurescript.org/reference/documentation){target=_blank} for the JavaScript platform (JavaScript browser engines and node.js)

The essentail differences between Clojure & ClojureScript are the host platform (Java or JavaScript) and the type of applications & services built with each language.

ClojureScript is predominately used for front-end applications, although can also be used as full stack solutions using a Clojure or node.js back-end server.

??? INFO "Minor Language differences"
    Due to differences between the Java and JavaScript host platforms, a small number of differences occur between Clojure and ClojureScript development.

    [:fontawesome-solid-book: ClojureScipt differences from Clojure](https://www.clojurescript.org/about/differences){target=_blank .md-button}

    Code which is independent of host can be written in Clojure common files, i.e. `*.cljc` file name extension.


## Learning ClojureScipt

[:fontawesome-solid-book-open: Learning ClojureScript Section](/clojurescript/introduction/learn-clojurescript/){target=_blank .md-button}


## Development Tools

[:fontawesome-solid-book-open: Clojure aware Editors](https://practical.li/clojure/clojure-editors/) also support ClojureScript. Use an editor most familiar with to minimise the initial learning curve.

Clojure aware editors have the same core functionality, so initial choice is not that important.  As experience of ClojureScript grows, additional features can become valuable and a review of editor tooling can be done with more insight and understanding.


## Build Automation

ClojureScript is trans-piled (compiled) into JavaScript before running in a JavaScript browser engine or on node.js.

The main tools to support the ClojureScript workflow:

* Figwheel - ClojureScript focused with the ability to bundle JavaScript npm packages (typically the simplest approach)
* Shadow-cljs - implementation of ClojureScipt for node.js and therefore deeply integrated into the npm infrastructure (initially more complex but potential simpler when managing a significant amount of npm packages and dependencies)


### Fighweel

![figwheel logo name](https://raw.githubusercontent.com/practicalli/graphic-design/live/logos/practicalli-figwheel-logo-name.svg){align=right loading=lazy style="height:92;width:92px"}

[Figwheel](https://figwheel.org/) is a simple approach and doesn't require node.js. ClojureScript applications can be built without JavaScript.  Figwheel does enabled use of npm packages via bundle though, should JavaScript packages be valuable to add.

[:fontawesome-brands-github: figwheel-template](https://github.com/bhauman/figwheel-template){target=_blank} creates ClojureScript projects with figwheel configuration and optionally react, reagent, rum and bundle (webpack) options.

[Figwheel](https://figwheel.org/){target=_blank .md-button}
[:fontawesome-brands-github: Figwheel Template](https://github.com/bhauman/figwheel-template){target=_blank .md-button}

??? INFO "Figwheel-main is library to use for Figwheel"
    Fighweel-main has replaced the figwheel library (now considered deprecated) and is a large rewrite of the tooling, providing a greatly enhanced experience.


### Shadow-cljs

Shadow-cljs is effectively built on top of node.js and therefore more integrated.  Assumes that node.js is well understood and significant use of JavaScript npm packages will be used

Read the user guide in detail to avoid common issues when starting

[Shadow-cljs User Guide](https://shadow-cljs.github.io/docs/UsersGuide.html){target=_blank .md-button}


## Common Libraries

As with any language, there are a wide range of choice for libraries to help build apps and many types of apps that can be built (UI / full-stacl / backend).

[:fontawesome-brands-github: reagent](https://reagent-project.github.io/) is the most commonly used ClojureScript library for front-end apps, especially single page applications.  reagent takes a react.js like approach.

[:fontawesome-brands-github: re-frame](http://day8.github.io/re-frame/) builds upon reagent and supports the building of more complex UIs and stateful workflows.

[:fontawesome-brands-github: reitit-frontend](https://github.com/metosin/reitit) to define routing for URIs to support navigation within a ClojureScript app.

[reagent](https://reagent-project.github.io/){target=_blank .md-button}
[reframe](http://day8.github.io/re-frame/){target=_blank .md-button}
[rum](https://github.com/tonsky/rum){target=_blank .md-button}
[reitit-frontend](https://github.com/metosin/reitit){target=_blank .md-button}
