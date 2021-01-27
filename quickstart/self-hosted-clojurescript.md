# Self Hosted Clojurescript

Ever since [ClojureScript was able to compile itself](http://swannodette.github.io/2015/07/29/clojurescript-17) there has been the idea of building and running Clojurescript projects without dependency on Java. 

[Planck](http://planck-repl.org/) and [Lumo](https://github.com/anmonteiro/lumo) can run ClojureScript via the REPL or run ClojureScript scripts and now Lumo version 1.2.0 supports compiling an entire ClojureScript project, just like the regular JVM-based ClojureScript compiler. 

This has been achieved by porting the JVM-based code in the ClojureScript compiler to work under Lumo and use the Node.js platform. 

> Self hosted Clojurescript is still a hosted language, just its hosted on a Javascript platform, in this case [node.js](https://nodejs.org/)

> Install Lumo 1.2.0 on Homebrew master with `brew install --HEAD lumo`


## Optimised builds with Google Clojure compiler

Using `google-closure-compiler-js` the generated JavaScript can be minified and highly optimised via dead-code elimination, ensuring only the code you actually use is included in the final javascript file.


This port has been generally straightforward, changing the synchronous JVM build API to the self-hosted ClojureScript asynchronous API has represented the most amount of work so far.


## No external dependencies

Compiling ClojureScript projects with Lumo requires no external dependencies (such as the Google Closure Library) apart from those required by the projects themselves.  All the necessary compiler dependencies are bundled within the single Lumo executable.

## Example Build Script

Taking the example from the ClojureScript Quick Start guide, simply change the `cljs.build.api` to `lumo.build.api`.  This example script will also use advanced optimisations so we can see the JavaScript version of the Google Closure Compiler in action.

```clojure
(require '[lumo.build.api :as b])

(b/build "src"
  {:main 'hello-world.core
   :output-to "main.js"
   :optimizations :advanced
   :target :nodejs})
```

## Running The Build

Run the build script with Lumo, adding the `src` folder to the classpath with `--classpath` command line option so Lumo can find the project.

```bash
$ lumo --classpath src build.cljs
```


> **Hint** run `lumo -h` to see all the lumo options

## Run your Clojurescript project

Run the compiled project with node.js using the command

```bash
node main.js
```

## Caveats

Lumo currently ships with its own version of the ClojureScript compiler, so for now its not possible to compile ClojureScript projects against any other versions. This does avoid having any external dependencies when compiling ClojureScript projects with Lumo though.

The Google Closure Compiler JS is a JavaScript port of the Java version, generated using GWT. It take longer to optimize code when compared to the Java version. It also ships with fewer features than its Java counterpart as not every feature included in the Java version is portable to JavaScript.

There is a large amount of work remaining to achieve feature parity with the current ClojureScript compiler on the JVM.  This feature of Lumo should therefor be considered pre-alpha

Please report issues, and if you want to help, do get in touch (e.g. on Twitter)!
