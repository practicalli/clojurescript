# Install ClojureScript

[:fontawesome-solid-book-open: Practicalli Clojure install guide](https://practical.li/clojure/install/clojure-cli/){target=_blank} provides the basis for development of ClojureScript projects.

ClojureScript is specified as a dependency in projects, which contains the language and basic tools for building projects.

[:globe_with_meridians: Google Closure tools](https://developers.google.com/closure) compiles ClojureScript into JavaScript. Compilation options can remove redundant code and minimise code to optimise download speed of the resulting JavaScript.  The compiler also checks syntax, variable references & types and warns about common JavaScript pitfalls.

[Figwheel-main](/clojurescript/figwheel-main/) provides a comprehensive tool for building ClojureScript applications. Changes are automatically reloaded in the browser on file save for instant feedback during development.  JavaScript packages can be included via [:globe_with_meridians: CLJSJS](https://cljsjs.github.io/) or [:globe_with_meridians: NPM](https://figwheel.org/docs/npm.html)


| Requirement                                                                     | Description                                                                              |
|---------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| [Java](https://practical.li/clojure/install/java/){target=_blank}               | ClojureScript tooling predominantly written in Clojure and requires Java Virtual Machine |
| [Clojure CLI](https://practical.li/clojure/install/clojure-cli/){target=_blank} | Tools for running and working with Clojure & ClojureScript projects                      |
| [Figwheel-main](/clojurescript/figwheel-main/)                         | Continuous Build tool for ClojureScript (library project dependency)                     |
| [Editor](https://practical.li/clojure/clojure-editors/){target=_blank}          | An editor that connects to the ClojureScript REPL and provides language support          |
| [Browser Tools](/clojurescript/install/browser-devtools/)                       | Browser specific development tool                                                        |


![ClojureScript conceptual architecture](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/clojurescript/clojurescript-concept-architecture.png)

!!! HINT "Shadow-cljs for hybrid JavaScript / ClojureScript development"
    [shadow-cljs](https://github.com/thheller/shadow-cljs){target=_blank} can be used instead of Figwheel to manage a ClojureScript projects.  Read the [Shadow CLJS user guide](https://shadow-cljs.github.io/docs/UsersGuide.html){target=_blank} in detail to understand how to manage projects with this tool.

## References

[Browser Support for JavaScript Features](https://caniuse.com/?search=JavaScript){target=_blank .md-button}

[Browser support for JavaScript APIs](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Browser_support_for_JavaScript_APIs){target=_blank .md-button}

[Hello ClojureScript! test dev tool support](https://firefox-dev.tools/debugger-examples/examples/clojurescript/hello.html){target=_blank .md-button}
