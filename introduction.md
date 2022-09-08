![Practicalli ClojureScript book banner](https://raw.githubusercontent.com/practicalli/graphic-design/live/book-covers/practicalli-clojurescript-book-banner-alpha.png)


[ClojureScript](https://clojurescript.org/) is an implementation of the [Clojure](https://clojure.org/) functional programming language for [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript) platforms, web browser JavaScript engines and  server-side node.js.

Discover the joy of ClojureScript for building [single page applications](https://en.wikipedia.org/wiki/Single-page_application), complex UI's, lightweight services and server side web applications.  Design approaches common to ClojureScript & React will be covered along the way.

Projects covered here focus on the [Figwheel-main](https://figwheel.org/) development tool, the reagent library for react.js style applications, hiccup syntax for html content and ClojureScript code.

> JavaScript npm packages can be used with Figwheel-main, however, this guide focuses on ClojureScript where ever possible

![ClojureScript REPL driven development with Figwheel-main](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/clojurescript-repl-driven-development-lifecycle-concept.png)

## Example websites
* [Practicalli Landing page](https://practicalli.github.io/)
* [ClojureBridgeLondon](https://clojurebridgelondon.github.io/workshop/additional-projects/clojurebridge-website/)

## Requirements
Follow the [Practicalli Clojure install instructions](http://practicalli.github.io/clojure/clojure-cli/install/) to set up a Clojure environment.  ClojureScript tools depend on Clojure and Java, although there are [self-hosted environments](/quickstart/self-hosted-clojurescript.html).

A [Clojure aware editor](https://practicalli.github.io/clojure/clojure-editors/) is highly recommend along with [web browser development tools](install/browser-devtools.html) to provide even greater feedback from the running application.

<!-- TODO: add Firefox dev tools to browser DevTools page -->

[![Built with Spacemacs](https://cdn.rawgit.com/syl20bnr/spacemacs/442d025779da2f62fc86c2082703697714db6514/assets/spacemacs-badge.svg)](https://practicalli.github.io/spacemacs/)


> #### Warning:: Content being refreshed
>  Many enhancements have happened to ClojureScript since this book was created, especially around [shadow-cljs](https://shadow-cljs.github.io/docs/UsersGuide.html) which is not yet covered.
>
> The most relevant content includes the [TicTacToe game with ClojureScript, Reagent and Scalable Vector Graphics](/reagent-projects/tic-tac-toe/index.html), the [Practicalli ClojureScript YouTube playlist](https://youtube.com/playlist?list=PLpr9V-R8ZxiBPv18gm9h1-eIWP1miwWh2) and [building ClojureScript websites](https://clojurebridgelondon.github.io/workshop/additional-projects/clojurebridge-website/).

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


> #### Hint::In need of tight integration with npm?
> Follow the [shadow-cljs documentation](http://shadow-cljs.org/) carefully and in detail if you wish your ClojureScript applications that work hand-in-hand with NPM and Node.js.  Ensure the project runs on the command line first, before trying to run the project from an editor.  Also check the documentation for specific configuration to ensure your chosen editor will work correctly with shadow-cljs


## Creative commons license

<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/">
<a href="http://creativecommons.org/licenses/by-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">
<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"></a>
 <a property="dct:title" rel="cc:attributionURL" href="https://github.com/practicalli/clojurescript">Practicalli ClojureScript </a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://practical.li">Practicalli</a> is licensed under <a href="http://creativecommons.org/licenses/by-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-SA 4.0 </a></p>
