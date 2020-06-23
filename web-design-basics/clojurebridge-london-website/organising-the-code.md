# Re-organising the code a little

Create comments to make it easier to identify the specific parts of the code

> #### Hint::Good structure helps refactor later
> Having an organised structure to your code helps you maintain the code and help you refactor code into multiple namespaces.


## Rename main component to landing-page

To make our code clearer, rename `hello-world` function to `landing-page`

```clojure
(defn landing-page []
  [:div
   [:h1 (:text @app-state)]
   [:h3 "Live reloading in the REPL makes web development fun!"]])
```

And update the `mount` function to use this new function name as the main component

```clojure
(defn mount [el]
  (reagent/render-component [landing-page] el))

```

## Create a system section

Move the `get-app-element` to the other mount / reagent functions and call that section System

```clojure
;; System
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

(defn get-app-element []
  (gdom/getElement "app"))

(defn mount [el]
  (reagent/render-component [landing-page] el))

```

## Add a date/time stamped reload message

As a quick sanity check, add a date / time stamp to the println message at the top of the file, so you can see the time figwheel reloads the page in the REPL output.

```clojure
;; simple debug statement for each build
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

(println (js/Date.) "Reloading: src/clojurebridge_landing_page/core.cljs")
```


## Final result

After all the changes the file should look as follows

```clojure
(ns ^:figwheel-hooks clojurebridge-landing-page.core
  (:require
   [goog.dom :as gdom]
   [reagent.core :as reagent :refer [atom]]))

;; simple debug statement for each build
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

(println (js/Date.) "Reloading: src/clojurebridge_landing_page/core.cljs")


;; Application state
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

;; define your app data so that it doesn't get over-written on reload
(defonce app-state (atom {:text "Hello world!"}))


;; Helper functions
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

(defn multiply [a b] (* a b))


;; Content components
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

(defn landing-page []
  [:div
   [:h1 (:text @app-state)]
   [:h3 "Live reloading in the REPL makes web development fun!"]])


;; System
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

(defn get-app-element []
  (gdom/getElement "app"))

(defn mount [el]
  (reagent/render-component [landing-page] el))

(defn mount-app-element []
  (when-let [el (get-app-element)]
    (mount el)))

;; conditionally start your application based on the presence of an "app" element
;; this is particularly helpful for testing this ns without launching the app
(mount-app-element)

;; specify reload hook with ^;after-load metadata
(defn ^:after-load on-reload []
  (mount-app-element)
  ;; optionally touch your app-state to force rerendering depending on
  ;; your application
  ;; (swap! app-state update-in [:__figwheel_counter] inc)
)
```
