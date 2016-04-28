# Serving assets

It is recommended that if you start needing a server to serve your ClojureScript assets that you just bite the bullet and write your own. But for convenience Figwheel has a built-in webserver. In order to use it you will have to place your assets in `resources/public`.

Following the example we are using you would need to make these changes:

Move your assets into `resources/public`:

```bash
mkdir -p resources/public
$ mv index.html css resources/public
```

Now you need to change your build config to output your compiled ClojureScript to `resources/public` as well. For good measure we will place them in a `cljs` directory.

```clojure
(defproject hello-seymore "0.1.0-SNAPSHOT"
  :dependencies [[org.clojure/clojure "1.7.0"]
                 [org.clojure/clojurescript "1.7.170"]
                 [sablono "0.3.6"]]
  :plugins [[lein-figwheel "0.5.0-1"]]
  :clean-targets [:target-path "out" "resources/public/cljs"] ;; Add "resources/public/cljs"
  :cljsbuild {
    :builds [{:id "dev"
              :source-paths ["src"]
              :figwheel true
              :compiler {:main hello-seymore.core 
                         ;; add the following 
                         :asset-path "cljs/out"
                         :output-to  "resources/public/cljs/main.js"
                         :output-dir "resources/public/cljs/out"} 
             }]
   }
   :figwheel {
      :css-dirs ["resources/public/css"]
   }
)
```

So now we have changed where the compiler is placing the compiled assets. It's very important to get `:asset-path` correct otherwise `main.js` will have code that doesn't point to your compiled assets and nothing will work. It is also important to add our new target path to the `:clean-targets`, otherwise `lein clean` won't work.

Since we changed the location of `main.js`, we need to reflect that in `index.html`:

```html
<!DOCTYPE html>
<html>
  <head>
    <link href="css/style.css" rel="stylesheet" type="text/css"> 
  </head>
  <body>
    <div id="app"></div>
    <script src="cljs/main.js" type="text/javascript"></script> ;; <-- changed to "cljs/main.js"
  </body>
</html>
```
 
Now you can restart Figwheel.

You can now find your application at `http://localhost:3449/index.html`
