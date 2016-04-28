# Create build file


As ClojureScript is a Clojure library, a simple build tool can be easily scripted in a few lines of *Clojure*. 

Create a file called `build.clj` in the `cljs_compiler` directory and add the following Clojure code:

```clj
(require 'cljs.build.api)

(cljs.build.api/build "src" {:output-to "out/main.js"})
```

> **Hint** In order to compile the ClojureScript code, we use the `build` function from the library `cljs.build.api`.  To access the functions of this library we use the `require` function.  This is similar to _import_ or _include_ in other languages.

The `cljs.build.api/build` function takes two arguments: the directory to compile and a map of options. In our code we include the option `:output-to` that specifies where to write the JavaScript.

