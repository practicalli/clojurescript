# Practicalli ClojureScript

![Practicalli ClojureScript book banner](https://raw.githubusercontent.com/practicalli/graphic-design/live/book-covers/practicalli-clojurescript-book-banner-alpha.png)


[ClojureScript](https://clojurescript.org/) is an implementation of the [Clojure](https://clojure.org/) functional programming language for [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript) platforms, web browser JavaScript engines and  server-side node.js.

Discover the joy of ClojureScript for building [single page applications](https://en.wikipedia.org/wiki/Single-page_application), complex UI's, lightweight services and server side web applications.  Design approaches common to ClojureScript & React will be covered along the way.

Projects covered here focus on the [Figwheel-main](https://figwheel.org/) development tool, the reagent library for react.js style applications, hiccup syntax for html content and ClojureScript code.

> JavaScript npm packages can be used with Figwheel-main, however, this guide focuses on ClojureScript where ever possible

![ClojureScript REPL driven development with Figwheel-main](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojurescript/clojurescript-repl-workflow-concept.png)


## Example websites

[:fontawesome-brands-github: Practicalli Landing page](https://github.com/practicalli/practicalli.github.io){target=_blank .md-button}
[:fontawesome-brands-github: ClojureBridgeLondon](https://github.com/ClojureBridgeLondon/clojurebridge-landing-page){target=_blank .md-button}


## Requirements

Follow the [Practicalli Clojure install instructions](http://practicalli.github.io/clojure/clojure-cli/install/) to set up a Clojure environment.  ClojureScript tools depend on Clojure and Java, although there are [self-hosted environments](/quickstart/self-hosted-clojurescript.html).

A [Clojure aware editor](https://practicalli.github.io/clojure/clojure-editors/) is highly recommend along with [web browser development tools](install/browser-devtools.html) to provide even greater feedback from the running application.

<!-- TODO: add Firefox dev tools to browser DevTools page -->

??? HINT "Need tight integration with npm?"
    ![Shadow-Cljs logo](https://raw.githubusercontent.com/thheller/shadow-cljs/master/src/main/shadow/cljs/devtools/server/web/resources/img/shadow-cljs.png){align=right loading=lazy}
    [shadow-cljs](http://shadow-cljs.org/) is built with node.js and NPM and so has deep integration with JavaScript packages, an advantage if a project benefits from significant use of node.js packages.

    Follow the [shadow-cljs documentation](http://shadow-cljs.org/) carefully and in detail for a smooth experience.  Ensure the project runs on the command line first, before trying to run the project from an editor.  Also check the documentation for specific configuration to ensure your chosen editor will work correctly with shadow-cljs


!!! Warning "Content being refreshed"
    Many enhancements have happened to ClojureScript since this book was created, especially around [shadow-cljs](https://shadow-cljs.github.io/docs/UsersGuide.html) which is not yet covered.

    The most relevant content includes the [TicTacToe game with ClojureScript, Reagent and Scalable Vector Graphics](/reagent-projects/tic-tac-toe/index.html), the [Practicalli ClojureScript YouTube playlist](https://youtube.com/playlist?list=PLpr9V-R8ZxiBPv18gm9h1-eIWP1miwWh2) and [building ClojureScript websites](https://clojurebridgelondon.github.io/workshop/additional-projects/clojurebridge-website/).

## Additional Resources

**Learning ClojureScript**

* [ClojureScript Unraveled](http://funcool.github.io/clojurescript-unraveled/)
* [ClojureScript Koans](http://clojurescriptkoans.com/)
* [Reagent Cookbook](https://github.com/reagent-project/reagent-cookbook)

**Tooling**

* [figwheel-main](https://figwheel.org/) - instant feedback for ClojureScript development
* [figwheel-main project template](https://github.com/bhauman/figwheel-main-template) - quickly create a figwheel-main based ClojureScript project

**Community**

* [Cljs js](http://cljsjs.github.io/) - javascript foreigner libraries for ClojureScript

**Commercial courses**

* [Jacek Schae - Reagent, Reframe, Reitit](https://www.jacekschae.com/)


## Creative commons license

<div style="width:95%; margin:auto;">
  <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>
  This work is licensed under a Creative Commons Attribution 4.0 ShareAlike License (including images & stylesheets).
</div>

[![Built with Spacemacs](https://cdn.rawgit.com/syl20bnr/spacemacs/442d025779da2f62fc86c2082703697714db6514/assets/spacemacs-badge.svg)](https://practicalli.github.io/spacemacs/)
