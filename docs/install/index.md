# Installing ClojureScript development tools

![ClojureScript conceptual architecture](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/clojurescript/clojurescript-concept-architecture.png)

Follow the [Practicalli Clojure - install Clojure tools](https://practicalli.github.io/clojure/clojure-tools/install/) guide to create a ClojureScript, which requires [Java](https://practicalli.github.io/clojure/clojure-tools/install/java.html), [Clojure](https://practicalli.github.io/clojure/clojure-tools/install/clojure.html) and a [ClojureScript aware editor](https://practicalli.github.io/clojure/clojure-editors/).

ClojureScript is specified as a dependency in projects, which contains the language and basic tools for building projects.

Figwheel-main is used to provide a comprehensive tool for building ClojureScript applications and supports REPL driven development and hot-loading of changes in the browser as the code is developed.

[practicalli/clojure-deps-edn](https://github.com/practicalli/clojure-deps-edn) GitHub repository contains the Clojure CLI user level configuration used in this guide and issues and pull requests can also be made there.

| Requirement                                                                           | Description                                                                                    |
|---------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| [Java](https://practicalli.github.io/clojure/clojure-cli/install/java.html)         | ClojureScript tooling is predominantly written in Java                                         |
| [Clojure CLI](https://practicalli.github.io/clojure/clojure-cli/install/clojure.html) | Tools for running and working with Clojure & ClojureScript projects                            |
| [Figwheel-main](figwheel-main-projects/)                                              | Build and hot-loading environment for ClojureScript (add library as project dependency)        |
| [ClojureScript editor](https://practicalli.github.io/clojure/clojure-editors/)        | An editor that connects to the ClojureScript REPL and provides language support                |
| Web Browser (Firefox, Chrome, chromium)                                               | Host platform for JavaScript                                                                   |

> HINT: [shadow-cljs](https://github.com/thheller/shadow-cljs) can be used instead of Figwheel to manage a ClojureScript projects.  Read the [Shadow CLJS user guide](https://shadow-cljs.github.io/docs/UsersGuide.html) in detail to understand how to manage projects with this tool.

![ClojureScript browser support](/images/web-browser-support-banner.png)

ClojureScript uses the [Google Closure tools](https://developers.google.com/closure) to compile ClojureScript to JavaScript which will run on a wide range of web browsers.

The [Google Closure tools](https://developers.google.com/closure) removes any code that is never called (dead code) and minimises the remaining code to optimise download speed.  The compiler also checks syntax, variable references, and types, and warns about common JavaScript pitfalls.

* [Can I use JavaScript ?](https://caniuse.com/?search=JavaScript)
* [Browser support for JavaScript APIs](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Browser_support_for_JavaScript_APIs)
* [Hello ClojureScript!](https://firefox-dev.tools/debugger-examples/examples/clojurescript/hello.html) - example project for testing dev tool support in browser
