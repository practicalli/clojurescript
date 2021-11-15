![ClojureScript and Figwheel-main banner](https://raw.githubusercontent.com/practicalli/graphic-design/live/banners/clojuresript-figwheel.png)

A [ClojureScript](https://clojurescript.org/) project should contain dependencies for the Clojure and ClojureScript libraries, which are managed by the build tool (Clojure CLI tools or Leiningen) just like any other dependency.

figwheel-main provides additional tooling for REPL driven development, including live updates to the browser REPL and test runner.

Use the [`figwheel-main` template](https://github.com/bhauman/figwheel-main-template) to generate a working ClojureScript project with Figwheel-main, optionally including [reagent](https://reagent-project.github.io/) and other react.js style libraries.


## Figwheel-main

Figwheel Main compiles the project when first run and creates a JavaScript application that is launched in the browser.

On every save of ClojureScript code figwheel-main automatically compiles the changes and injects them into the JavaScript application running in the browser, providing instant feedback as the project developers.

{% youtube %}
https://youtu.be/j-kj2qwJa_E
{% endyoutube %}

> #### Hint::figwheel and figwheel-main
> figwheel is the original tool that has been replaced by figwheel-main.  The configuration between the two tools is incompatible, however, the ClojureScript code should work when migrated to a figwheel-main project configuration.


## Figwheel template & options

The [`figwheel-main` template](https://github.com/bhauman/figwheel-main-template) creates a Clojurescript project with configuration to run the Figwheel-main build tool.

The figwheel-main template takes [several options](https://github.com/bhauman/figwheel-main-template#options), `--reagent`, `--rum` and `--om`, each of which creates a basic project with the respective libraries.

The `--` between the project name and `--reagent` option ensures this option is passed to the template, rather than being passed to Leiningen itself.


## Working with Editors
Most [Clojure aware editors](https://practicalli.github.io/clojure/clojure-editors/) support ClojureScript too.

> ####Hint::Ensure project runs locally before running from an editor
> Running a ClojureScript project on the command line is a quick way to ensure everything is working before considering running the project via an editor.


## Reference

* [Interactive programming Flappy Birds in ClojureScript](https://www.youtube.com/watch?v=KZjFVdU8VLI)
* [Clojure West 2015 - Developing ClojureScript with Figwheel](https://www.youtube.com/watch?v=j-kj2qwJa_E)


> #### Hint::Google Closure Compiler
> ClojureScript uses the Google Closure compiler and build tools that require a Java Virtual machine.  The Google Clojure tools provide highly optimal JavaScript code and eliminates and code not called from the final build.
>
> Self-hosted options include Plank and Lumo.  [ClojureScript Next](http://swannodette.github.io/2015/07/29/clojurescript-17/) and [Bootstrapped ClojureScript FAQ](https://github.com/clojure/clojurescript/wiki/Bootstrapped-ClojureScript-FAQ) elaborate on the advantages and challenges for self-hosted ClojureScript.
