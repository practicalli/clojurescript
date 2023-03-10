# Production Build


You may have noticed that `out` contains a lot of
JavaScript. Fortunately the ClojureScript compiler generates output
optimized for the Google Closure Compiler. The Google Closure Compiler
performs many optimizations, but the most significant for browser-based
clients are minification and dead code elimination.

Let's make a new helper build script `release.clj`, it should
look like the following:

```clojure
(require 'cljs.build.api)

(cljs.build.api/build "src"
  {:output-to "out/main.js"
   :optimizations :advanced})

(System/exit 0)
```

Under `:advanced` optimizations `:main` is not needed as advanced
compilation creates a single JavaScript artifact. We also add a
`(System/exit 0)` as the Google Closure Compiler creates a thread pool
that isn't shutdown - we know we're done we can just exit.

Let's remove the dev time REPL bits from `src/hello_world/core.cljs`:

```clojure
(ns hello-world.core)

(enable-console-print!)

(println "Hello world!")
```

Let's create a release build:

```clojure
java -cp cljs.jar:src clojure.main release.clj
```

This process will take significantly longer which is why we don't use
this compilation mode for development.

Open `index.html`, you should still see `"Hello world!"` printed.

Examine `out/main.js`, the file size should be around 80K. If you zip
this file you'll see that it's around 19K. This is significantly
smaller than a jQuery dependency yet when using ClojureScript you have
implicit dependencies on the entire ClojureScript standard library
(10KLOC) and the Google Closure Library (300KLOC). You can thank
dead code elimination.
