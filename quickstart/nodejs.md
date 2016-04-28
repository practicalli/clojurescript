# Running ClojureScript on Node.js


First install Node.js. For instructions on installing Node.js, see the
[Node.js wiki](https://github.com/joyent/node/wiki/Installation). Only
the current stable versions of Node.js (>= `0.12.X`) are supported at
this time. Your `src/hello_world/core.cljs` should look like the following:

```clj
(ns hello-world.core
  (:require [cljs.nodejs :as nodejs]))

(nodejs/enable-util-print!)

(defn -main [& args]
  (println "Hello world!"))

(set! *main-cli-fn* -main)
```

Make a build helper file called `node.clj`:

```clj
(require 'cljs.build.api)

(cljs.build.api/build "src"
  {:main 'hello-world.core
   :output-to "main.js"
   :target :nodejs})
```

The only differences are that we had to specify a `:nodejs` target and
we do not output `main.js` to the `out` directory. This is important
due to the way that Node.js resolves JavaScript source files.

Node.js has great source mapping support, in order to enable it just
install `source-map-support`:

```
npm install source-map-support
```

Let's build your Node project:

```
java -cp cljs.jar:src clojure.main node.clj
```

You can run your file with:

```
node main.js
```

> **Note**: Under Node.js there is little reason to use advanced optimizations. While advanced optimizations does apply performance related optimizations, these are now largely obviated by optimizations present in modern JavaScript virtual machines like V8, SpiderMonkey, and JavaScriptCore. For Node.js, `:simple` or `:none` optimizations suffice and using them removes the need for extra steps like supplying an externs file.



### Node.js REPL

Running a Node.js REPL is much simpler than running a browser
REPL. Create a helper build file called `node_repl.clj` that looks
like the following:

```clj
(require 'cljs.repl)
(require 'cljs.build.api)
(require 'cljs.repl.node)

(cljs.build.api/build "src"
  {:main 'hello-world.core
   :output-to "out/main.js"
   :verbose true})

(cljs.repl/repl (cljs.repl.node/repl-env)
  :watch "src"
  :output-dir "out")
```

There's no need to add any REPL specific bits to
`src/hello_world/core.cljs`, make sure it looks as described in the
previous section.

Let's start the REPL:

```
rlwrap java -cp cljs.jar:src clojure.main node_repl.clj
```

All the previously described REPL interactions for the browser should work.
