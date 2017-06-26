# Use Local State In Session Form


> #### Note::Refactor session-add component
> Change `om/IRender` to `om/IRenderState`.  Add `state` to the render functions arguments
>
> Add a ':value' key to each of the form elements, pulling data from the local state.


<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

```clj
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
    om/IRenderState
    (render-state [_ state]
      (dom/div nil
        (dom/h3 nil "New Session")
        (dom/form #js {:className "form-horizontal"}
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:title state)
                          :placeholder "Session Title"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:speaker-name state)
                          :placeholder "Speaker Name"})
          (dom/textarea #js {:className "form-control"
                             :value (:description state)
                             :placeholder "Session Description"
                             :rows "5"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:speaker-biography state)
                          :placeholder "Speaker Biography"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:twitter-handle state)
                          :placeholder "Twitter Handle"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:github-handle state)
                          :placeholder "Github Handle"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:speaker-website state)
                          :placeholder "Speaker Website"})
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


> #### Hint::
> The local state is now locked into the form.  It still needs to be locked the other way around.
