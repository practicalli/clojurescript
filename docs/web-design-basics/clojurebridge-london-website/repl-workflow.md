# REPL Workflow

Calling `(mount-app-element)` will update the application with any evaluated changes, regardless of whether the file has been saved.

When saving a file, Figwheel will update the running application in the browser with any code changes.

Updating the state updates the running application in the browser.


## Reloading code

Make a change to the code, e.g. updating a function definition to display a different string for a sub-heading

```clojure
(defn hello-world []
  [:div
   [:h1 (:text @app-state)]
   [:h3 "Evaluate code in the REPL can update your ClojureScript application in the browser"]])
```

Update the application in the browser by evaluating the call to `(mount-app-element)`


## Testing different states

Changes to the application state, held in the `app-state` atom, trigger reagent to update any components (functions) that are using that data and redrawing that component in the live running application

Changing the value provides a convenient way to test the application in different states and see the results immediately.

A rich comment block can be used to hold different states that are useful to set in the application, using either a `swap!` or `reset!` expression.

```clojure
(comment

  (reset! app-state {:text "Welcome to the Figwheel REPL experience"})

) ;; End of rich comment block
```



## Testing without the app element
`(mount-app-element)` will conditionally start the application based on the presence of an "app" element in the index.html page.

When the "app" element is not there then the namespace can be tested without launching the application in the browser.



## Figwheel-main template reload code

When the `--reagent` option is used with the figwheel-main template then several function definitions are included to help with reloading the application


`get-app-element` finds the "app" element in the `resources/public/index.html` page using the Google doom library

```clojure
(defn get-app-element []
  (gdom/getElement "app"))
```


`mount` passes the component to render to the reagent `render`function along with the element in the web page that defines where to inject the application.

The component is the function definition  that represents the entry point to the application.

```clojure

(defn mount [el]
  (rdom/render [hello-world] el))
```

`mount-app-element` uses the above two functions to start the application within the web page.

```clojure
(defn mount-app-element []
  (when-let [el (get-app-element)]
    (mount el)))
```

`(mount-app-element)` is called when the namespace is loaded to start the application within the web page.

`on-reload` is called every time Figwheel process reloads the application and can be used to add behaviour and state changes that should happen each time.  The commented example adds a counter so that the total number of times the application is reloaded is captured.

```clojure
;; conditionally start your application based on the presence of an "app" element
;; this is particularly helpful for testing this ns without launching the app
(mount-app-element)
;; - P9I: Reloads the app-element too, updating any evaluated definitions in the REPL

;; specify reload hook with ^;after-load metadata
(defn ^:after-load on-reload []
  (mount-app-element)
  ;; optionally touch your app-state to force rerendering depending on
  ;; your application
  ;; (swap! app-state update-in [:__figwheel_counter] inc)
)

```
