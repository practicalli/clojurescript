# Create Sessions Component

To keep components simple, we can factor out the specifics of displaying the session into its own component.

`om/build` builds a new instance of a component. It takes two arguments: the component function and the data to render with that component.

Whenever data changes, the built component will be rerendered. So if you call om/build a second time with different data, it will render again.



> #### Note::Create a new component to display session details
> Create a new component called `session-details` and move the code inside the for iteration to this new component.


<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

```clojure
(defn session-details [session owner]
  (reify
    om/IRender
    (render [_]
      (dom/div #js {:className "panel panel-primary"}
               (dom/h1 #js {:className "panel-heading"} (:title session))
               (dom/div #js {:className "panel-body"}
                        (dom/h3 nil (str "By " (:speaker-name session)))
                        (dom/div nil (:description session))
                        (dom/hr nil)
                        (dom/div nil (str "About " (:speaker-name session) ":"))
                        (dom/div nil (:speaker-biography session))
                        (dom/div nil (:twitter-handle session))
                        (dom/div nil (:github-handle session))
                        (dom/div nil (:speakers-website session)))))))


(defn root-component [app owner]
  (reify
    om/IRender
    (render [_]
      (dom/div #js {:className "container"}
               (dom/h1 #js {:className "jumbotron"} (:conference-name app))
               (for [session (:sessions app)]
                 (om/build session-details session))))))
```

There should be no difference in the look and feel of your application.  Your code is a little more modular now.

<!--endsec-->

