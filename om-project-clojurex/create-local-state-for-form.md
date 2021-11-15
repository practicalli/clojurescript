# Create Local State For Form

> #### Note::Create local state
> Use the `om/IInitState` interface to create a map containing the local state


<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

```clojure
(defn session-add [cursor component]
  (reify
    om/IInitState
    (init-state [this]
      {:title "title placeholder"
       :description "description placeholder"
       :speaker-name "speaker name placeholder"
       :speaker-biography "speaker biography placeholder"
       :twitter-handle "twitter placeholder"
       :github-handle "github placeholder"
       :speaker-website "website placeholder"})
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
          (dom/button #js {:className "btn btn-primary"
                           :onClick
                             (fn [e]
                               (.preventDefault e)
                               (om/transact! cursor :sessions
                                 (fn [session]
                                   ((fnil conj []) session
                                    {:title "title placeholder"
                                     :description "description placeholder"
                                     :speaker-name "speaker name placeholder"
                                     :speaker-biography "speaker biography placeholder"
                                     :twitter-handle "twitter placeholder"
                                     :github-handle "github placeholder"
                                     :speaker-website "website placeholder"}))))}
                      "Submit"))))))


```

<!--endsec-->
