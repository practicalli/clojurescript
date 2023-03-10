# Project Build file

Create a file called `project.clj` and add the following Clojure code:

```clojure
(defproject hello-figwheel "0.1.0-SNAPSHOT"
  :dependencies [[org.clojure/clojure "1.7.0"]
                 [org.clojure/clojurescript "1.7.170"]]
  :plugins [[lein-figwheel "0.5.0-1"]]
  :clean-targets [:target-path "out"]
  :cljsbuild {
    :builds [{:id "dev"
              :source-paths ["src"]
              :figwheel true
              :compiler {:main "hello-figwheel.core"}
             }]
   })
```

