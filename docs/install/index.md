# Install ClojureScript

[Practicalli Clojure install guide](https://practical.li/clojure/install/clojure-cli/){target=_blank} provides the basis for development of ClojureScript projects.

ClojureScript is specified as a dependency in projects, which contains the language and basic tools for building projects.

ClojureScript uses [Google Closure tools](https://developers.google.com/closure) to compile ClojureScript to JavaScript. [Google Closure compiler](https://developers.google.com/closure) can remove redundant code (code paths never used) and minimise code to optimise download speed.  The compiler also checks syntax, variable references & types and warns about common JavaScript pitfalls.

Figwheel-main provides a comprehensive tool for building ClojureScript applications. Changes are automatically reloaded in the browser on file save for instant feedback during development.  JavaScript packages can be included via [CLJSJS](https://cljsjs.github.io/) or [NPM](https://figwheel.org/docs/npm.html)

[Practicalli Clojure CLI Config](https://github.com/practicalli/clojure-deps-edn) GitHub repository contains the Clojure CLI user level configuration used in this guide and issues and pull requests can also be made there.

| Requirement                                                                          | Description                                                                              |
|--------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| [Java](https://practical.li/clojure/install/java/){target=_blank}                    | ClojureScript tooling predominantly written in Clojure and requires Java Virtual Machine |
| [Clojure CLI](https://practical.li/clojure/install/clojure-cli/){target=_blank}      | Tools for running and working with Clojure & ClojureScript projects                      |
| [Figwheel-main](/clojurescript/figwheel-main-projects/)                              | Continuous Build tool for ClojureScript (library project dependency)                     |
| [ClojureScript editor](https://practical.li/clojure/clojure-editors/){target=_blank} | An editor that connects to the ClojureScript REPL and provides language support          |
| [Web Browser Tools](/clojurescript/install/browser-devtools/)                        | Browser specific development tool                                                        |


![ClojureScript conceptual architecture](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/clojurescript/clojurescript-concept-architecture.png)

!!! HINT "Shadow-cljs for hybrid JavaScript development"
    [shadow-cljs](https://github.com/thheller/shadow-cljs){target=_blank} can be used instead of Figwheel to manage a ClojureScript projects.  Read the [Shadow CLJS user guide](https://shadow-cljs.github.io/docs/UsersGuide.html){target=_blank} in detail to understand how to manage projects with this tool.

## References

* [Can I use JavaScript ?](https://caniuse.com/?search=JavaScript){target=_blank}
* [Browser support for JavaScript APIs](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Browser_support_for_JavaScript_APIs){target=_blank}
* [Hello ClojureScript!](https://firefox-dev.tools/debugger-examples/examples/clojurescript/hello.html){target=_blank} - example project for testing dev tool support in browser
