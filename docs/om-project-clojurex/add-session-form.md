# Add Session Form

> #### Note::Create a Session Submission Form
> Create a `session-add` component with a `dom/form` that includes `dom/input` for all fields.  The session description can use a `dom/textarea`.


<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

```clojure
(defn session-add [session component]
  (reify
    om/IRender
    (render [_]
      (dom/div nil
               (dom/h3 nil "New Session")
               (dom/form #js {:className "form-horizontal"}
                         (dom/input #js {:type "text"
                                         :className "form-control"
                                         :placeholder "Session Title"})
                         (dom/input #js {:type "text"
                                         :className "form-control"
                                         :placeholder "Speaker Name"})
                         (dom/textarea #js {:className "form-control"
                                            :placeholder "Session Description"
                                            :rows "5"})
                         (dom/input #js {:type "text"
                                         :className "form-control"
                                         :placeholder "Speaker Biography"})
                         (dom/input #js {:type "text"
                                         :className "form-control"
                                         :placeholder "Twitter Handle"})
                         (dom/input #js {:type "text"
                                         :className "form-control"
                                         :placeholder "Github Handle"})
                         (dom/input #js {:type "text"
                                         :className "form-control"
                                         :placeholder "Twitter Handle"})
                         (dom/button #js {:className "btn btn-primary"}
                                     "Submit"))))))


(defn root-component [app owner]
  (reify
    om/IRender
    (render [_]
      (dom/div #js {:className "container"}
               (dom/h1 #js {:className "jumbotron"} (:conference-name app))
               (for [session (:sessions app)]
                 (om/build session-details session))
               (dom/hr nil)
               (om/build session-add app)))))

```
<!--endsec-->
