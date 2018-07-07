# Figwheel Helper Functions

The [lein-figwheel](https://github.com/bhauman/lein-figwheel) template provides several helper functions in `dev/user.clj` to start Figwheel and a Clojurescript REPL from a Clojure REPL.

In a development environment a Clojure REPL will start in `user` namespace, so the functions in `dev/user.clj` are available when you run a Clojure REPl in Spacemacs - `SPC m '`


```clojure
(ns user
  (:require
   [figwheel-sidecar.repl-api :as f]))

;; user is a namespace that the Clojure REPL loads if its available

;; Helper functions can also be added for starting and stopping a webserver or other development services


(defn fig-start
  "This starts the figwheel server and watch based auto-compiler."
  []
  (f/start-figwheel!))

(defn fig-stop
  "Stop the figwheel server and watch based auto-compiler."
  []
  (f/stop-figwheel!))

;; com.cemerick/piggieback is added as a :profile :dev :dependency to support an nREPL environment
(defn cljs-repl
  "Launch a ClojureScript REPL that is connected to your build and host environment."
  []
  (f/cljs-repl))
```


## Emacs & `clojurescript-jack-in`

You can use these Figwheel helper functions with Emacs & Cider (and Spacemacs) by adding the following function in your `init.el` configuration file (or ~/.spacmacs file in the `dotspacemacs/user-config` section)

```elisp
(setq cider-cljs-lein-repl
  "(do
    (user/fig-start)
    (user/cljs-repl))")
```

When you run the Emacs command `clojurescript-jack-in` the `cider-cljs-lein-repl` name is evaluated and the two helper functions are run one after the other.


## Atom and ProtoREPL

See the [ClojureScript section on Practicalli, ProtoREPL](https://practicalli.github.io/atom-protorepl/clojurescript/)
