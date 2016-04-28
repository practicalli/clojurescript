# Build Project


Now we have a build file, build the project as follows:

```shell
java -cp cljs.jar:src clojure.main build.clj
```

On Windows:
```shell
java -cp "cljs.jar;src" clojure.main build.clj
```

We invoke `java` and set the classpath to our JAR and the directory where our ClojureScript code lives. The `clojure.main`
argument in this case allows us to easily execute a Clojure file.

> **Debug Note**: If you encounter an error about `cljs.build.api` not being found, make sure that you didn't write `(require 'cljs.build.api')`, many popular text editors will emit a matching single quote even in their Clojure mode.

Control should return to the shell relatively quickly and you will have an `out` directory with compiled JavaScript including
your simple program. You will see that many files were produced in addition to the `out/main.js` we specified. We'll explain this
momentarily but first let's see how you can easily include the compiled output on a web page.
