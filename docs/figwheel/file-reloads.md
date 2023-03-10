# File Reloads


Figwheel normally reloads any file that has changed. If you want to
prevent certain files from being **reloaded** by figwheel, you can add
meta-data to the namespace declaration like so:

```clojure
(ns ^:figwheel-no-load example.core)
```

Figwheel will not load or reload files that haven't been required by
your application. If you want to force a file to be loaded when it
changes add the follwoing meta-data the namespace declaration of the file:

```clojure
(ns ^:figwheel-load example.core)
```

It can be very helpful to have a file reload every time a file changes
in your ClojureScript source tree. This can facilitate reloading your
main app and running tests on change.

To force a file to reload on every change:

```clojure
(ns ^:figwheel-always example.test-runner)
```


#### Using the ClojureScript REPL

When you run `lein figwheel` a REPL will be launched into your application.

You will need to open your application in a browser in order for the
REPL to connect and show its prompt.

This REPL is a little different than other REPLs in that it has live
compile information from the build process. This effectively means
that you will not have to call `(require` or `(load-namesapce` unless
it is a namespace that isn't in your loaded application's required
dependencies. In many cases you can just `(in-ns 'my.namespace)` and
everything you need to access will be there already.

The REPL doesn't currently have built-in readline support. To have a
better experience please install **rlwrap**. You can do this on OSX
using brew: `brew install rlwrap`.

When `rlwrap` is installed you can now execute lein figwheel as so:

```
$ rlwrap lein figwheel
```

This will give you a much nicer REPL experience with history and line
editing.
