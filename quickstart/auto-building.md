# Auto-building


The ClojureScript compiler supports incremental compilation. It's
convenient to have the ClojureScript compiler watch a directory
and recompile as needed. Let's make a new helper script `watch.clj`:

```clojure
(require 'cljs.build.api)

(cljs.build.api/watch "src"
  {:main 'hello-world.core
   :output-to "out/main.js"})
```

Let's start auto building:

```shell
java -cp cljs.jar:src clojure.main watch.clj
```

You should see output like the following:

```
Building ...
Reading analysis cache for jar:file:/.../cljs.jar!/cljs/core.cljs
Analyzing src/hello_world/core.cljs
... done. Elapsed 1.425505401 seconds
```

Edit `src/hello_world/core.cljs`. You should see recompilation output.

Terminate auto building (using `Ctrl-C`) before proceeding to the next section.

> **Further Reading**: While not required for the remainder of the Quick Start, it's highly recommended that you familiarize yourself with basics of [Google Closure Library](https://developers.google.com/closure/library/index). Many simple errors can be avoided by reinforcing your understanding of how Closure Library works.
