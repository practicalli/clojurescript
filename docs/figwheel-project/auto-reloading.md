# Auto Reloading

Figwheel will autoreload css as well. You will need to add some server level configuration to get this feature.

First create a CSS file `css/style.css`.

```css
body {
  background-color: yellow;
}
```

Edit the `project.clj`

```clojure
(defproject hello-seymore "0.1.0-SNAPSHOT"
  :dependencies [[org.clojure/clojure "1.7.0"]
                 [org.clojure/clojurescript "1.7.170"]
                 [sablono "0.3.6"]]
  :plugins [[lein-figwheel "0.5.0-1"]]
  :clean-targets [:target-path "out"]
  :cljsbuild {
    :builds [{:id "dev"
              :source-paths ["src"]
              :figwheel { :on-jsload "hello-seymore.core/render!" }
              :compiler {:main hello-seymore.core } 
             }]
   }
   :figwheel { ;; <-- add server level config here
     :css-dirs ["css"]
   }
)
```

And of course don't forget to add a link to your css in the `index.html`:

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- add link here -->
    <link href="css/style.css" rel="stylesheet" type="text/css"> 
  </head>
  <body>
    <script src="main.js" type="text/javascript"></script>
  </body>
</html>
```

Now restart Figwheel and edit the `style.css`:

```css
body {
  background-color: green;
}
```

Your page in the browser should now be green and not yellow. Without reloading the page!

### Opting out of autoreloading

You may not want to have your code auto-reloaded but still want to benefit from Figwheel's auto-building and its REPL.  All you have to do is add `:autoload false` to the `:figwheel` entry in your build config. 

In this case your build config would look like this:

```clojure
(defproject hello-seymore "0.1.0-SNAPSHOT"
  :dependencies [[org.clojure/clojure "1.7.0"]
                 [org.clojure/clojurescript "1.7.170"]
                 [sablono "0.3.6"]]
  :plugins [[lein-figwheel "0.5.0-1"]]
  :clean-targets [:target-path "out"]
  :cljsbuild {
    :builds [{:id "dev"
              :source-paths ["src"]
              :figwheel { :autoload false } ;; <<- add this
              :compiler {:main hello-seymore.core } 
             }]
   })
```
