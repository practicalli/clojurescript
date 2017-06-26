# Add Session Style

To make it easier to read the individual sessions, add a style called [panel](https://www.w3schools.com/bootstrap/bootstrap_panels.asp).  To make it interesting use a `primary-panel` style or one of the other coloured panels.

> #### Note::Add the Panel Prime style to each session
> Edit the `src/clojurex/cljs/core.cljs` file and update the `root-component` to include the `panel` style for each session


<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->


```clj
(defn root-component [app owner]
  (reify
    om/IRender
    (render [_]
      (dom/div #js {:className "container"}
        (dom/h1 #js {:className "jumbotron"} (:conference-name app))
        (for [session (:sessions app)]
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
              (dom/div nil (:speakers-website session)))))))))
```

<!--endsec-->


Take a look at your page and the sessions should all be wrapped by a panel.

![ClojureX Project - Bootstrap jumbotron](/images/clojurex-project-bootsrap-panel.png)

