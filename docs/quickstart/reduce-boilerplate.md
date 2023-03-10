# Reduce boilerplate


The previous section explained some important fundamental concepts around the Google Closure Library. However it also involved a
substantial amount of boilerplate. We can eliminate this boilerplate by specifying a `:main` entry point in the options that we pass to `cljs.build.api/build`. Let's do that now:

```clojure
(require 'cljs.build.api)

(cljs.build.api/build "src"
  {:main 'hello-world.core
   :output-to "out/main.js"})
```

Change your HTML to the following:

```html
<html>
    <body>
        <script type="text/javascript" src="out/main.js"></script>
    </body>
</html>
```

Rebuild on Mac or GNU/Linux:

```shell
java -cp cljs.jar:src clojure.main build.clj
```

On Windows:
```
java -cp "cljs.jar;src" clojure.main build.clj
```

Refresh the page and you should still see `"Hello world!"` printed to
the JavaScript console. If you examine `out/main.js` you'll see that
it writes out the boilerplate script tags for you. The previous contents of `main.js` are now in `out/cljs_deps.js`, which is loaded alongside our namespace by the new `out/main.js`.
