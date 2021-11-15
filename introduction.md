![Practicalli ClojureScript](/images/practicalli-clojurescript-book-banner.png)

[ClojureScript](https://clojurescript.org/) is an implementation of the [Clojure](https://clojure.org/) functional programming language for [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript) platforms (web browser, node.js, amazon lambda).

Discover the joy of ClojureScript for building [single page applications](https://en.wikipedia.org/wiki/Single-page_application), complex UI's, lightweight services and server side web applications.  Design approaches common to ClojureScript & React will be covered along the way.

Projects covered here focus on the [Figwheel-main](https://figwheel.org/) development tool, the reagent library for react.js style applications, hiccup syntax for html content and ClojureScript code.

> JavaScript npm packages can be used with Figwheel-main, however, this guide does not yet cover that topic.

![ClojureScript REPL driven development with Figwheel-main](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/clojurescript-repl-driven-development-lifecycle-concept.png)

## Example websites
* [Practicalli Landing page](https://practicalli.github.io/)
* [ClojureBridgeLondon](https://clojurebridgelondon.github.io/workshop/additional-projects/clojurebridge-website/)

## Requirements
Follow the [Practicalli Clojure install instructions](http://practicalli.github.io/clojure/clojure-tools/install/) to set up a Clojure environment.  ClojureScript tools depend on Clojure and Java, although there are [self-hosted environments](/quickstart/self-hosted-clojurescript.html).

A [Clojure aware editor](https://practicalli.github.io/clojure/clojure-editors/) is highly recommend along with [web browser development tools](install/browser-devtools.html) to provide even greater feedback from the running application.

<!-- TODO: add Firefox dev tools to browser DevTools page -->

[![Built with Spacemacs](https://cdn.rawgit.com/syl20bnr/spacemacs/442d025779da2f62fc86c2082703697714db6514/assets/spacemacs-badge.svg)](https://practicalli.github.io/spacemacs/)



> #### Warning:: Re-write planned for 2021
>  Many enhancements have happened to ClojureScript since this book was created, especially around [shadow-cljs](https://shadow-cljs.github.io/docs/UsersGuide.html) which is not yet covered.
>
> Content still relevant includes the [TicTacToe game with ClojureScript, Reagent and Scalable Vector Graphics](/reagent-projects/tic-tac-toe/index.html), the [Practicalli ClojureScript YouTube playlist](https://youtube.com/playlist?list=PLpr9V-R8ZxiBPv18gm9h1-eIWP1miwWh2) and [building ClojureScript websites](https://clojurebridgelondon.github.io/workshop/additional-projects/clojurebridge-website/).

## Additional Resources

**Learning ClojureScript**
* [ClojureScript Unraveled](http://funcool.github.io/clojurescript-unraveled/)
* [ClojureScript Koans](http://clojurescriptkoans.com/)
* [Reagent Cookbook](https://github.com/reagent-project/reagent-cookbook)

**Tooling**
* [figwheel-main](https://figwheel.org/) - instant feedback for ClojureScript development
* [figwheel-main project template](https://github.com/bhauman/figwheel-main-template) - quickly create a figwheel-main based ClojureScript project

**Community**
* [Official Google group](https://groups.google.com/forum/#!forum/clojurescript)
* [Cljs js](http://cljsjs.github.io/) - javascript foreigner libraries for ClojureScript

**Commercial courses**
* [Jacek Schae - Reagent, Reframe, Reitit](https://www.jacekschae.com/)


> #### Hint::Heavy use of npm libraries required?
> Follow the [shadow-cljs documentation](http://shadow-cljs.org/) carefully and in detail if you wish your ClojureScript applications that work hand-in-hand with NPM and Node.js.  Ensure the project runs on the command line first, before trying to run the project from an editor.  Also check the documentation for specific configuration to ensure your chosen editor will work correctly with shadow-cljs


## Creative commons license
<p xmlns:dct="http://purl.org/dc/terms/" xmlns:cc="http://creativecommons.org/ns#" class="license-text"><a rel="cc:attributionURL" href="https://practicalli.github.io/clojure/"><span rel="dct:title">Practicalli Clojure</span></a> by <a rel="cc:attributionURL" href="https://practicalli.github.io/"><span rel="cc:attributionName">Practicalli</span></a> Creative Commons Attribution Share-Alike 4.0 International<a href="https://creativecommons.org/licenses/by-sa/4.0"><img style="height:22px!important;margin-left: 3px;vertical-align:text-bottom;" src="https://search.creativecommons.org/static/img/cc_icon.svg" /><img  style="height:22px!important;margin-left: 3px;vertical-align:text-bottom;" src="https://search.creativecommons.org/static/img/cc-by_icon.svg" /><img  style="height:22px!important;margin-left: 3px;vertical-align:text-bottom;" src="https://search.creativecommons.org/static/img/cc-sa_icon.svg" /></a></p>
