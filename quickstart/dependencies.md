# Dependencies


ClojureScript supports a wide variety of options for including ClojureScript and JavaScript dependencies (see [[Dependencies]] for details). However the simplest approach is to include a properly packaged JAR on the classpath. [CLJSJS](http://cljsjs.github.io) provides a nice set of curated JavaScript libraries that suffices to demonstrate how dependencies are handled.

[React](http://facebook.github.io/react/) is a popular dependency for ClojureScript projects. [CLJSJS](http://cljsjs.github.io) provides a [bundled version](https://github.com/cljsjs/packages/tree/master/react). Let's see how to include it.

Grab the JAR from [Clojars](https://clojars.org):

```
curl -O https://clojars.org/repo/cljsjs/react/0.12.2-8/react-0.12.2-8.jar
```

Let's edit our simple program to look like the following so that React is properly required:

```clj
(ns hello-world.core
  (:require cljsjs.react))

(enable-console-print!)

(println "Hello React!")
```

Let's rebuild our project, all we need to do is extend our classpath to include the CLJSJS React JAR.

```
java -cp cljs.jar:src:react-0.12.2-8.jar clojure.main build.clj
```

If you refresh your `index.html` page you should see the usual React log indicating that React was successfully loaded.

If you have a few dependencies, one convention is to put them into a folder called `lib`. Then you can launch your scripts like so:

```
java -cp 'cljs.jar:lib/*:src' clojure.main build.clj
```

As your dependency graph becomes more sophisticated it may make sense to rely on Maven or Leiningen to manage dependencies for you. Please refer to [[Dependencies]] for a comprehensive tutorial. What follows is just the basics.

### Leiningen

All the commands above may be executed with the `run` feature of Leiningen. With Leiningen you do not need to specify the classpath.  For example for a REPL you would do something like the following from your project directory:

```
lein run -m clojure.main repl.clj
```

One important thing to remember with Leiningen is the `:source-paths` configuration parameter. The `:source-paths`, found in the project.clj, are appended to the classpath. For a ClojureScript build you should include all the source paths to your ClojureScript sources in the `:source-paths` parameter. The path "src" is included by default.

This is especially important if you use another path besides "src".

If you have any questions about the classpath you can see it easily by typing 
`lein classpath`.

