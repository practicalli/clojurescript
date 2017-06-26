# Connect Form To Local State


> #### Note::Use React's onClick event to connect form to local state
> Add the `:onChange` key and function to each part of the form, connecting that event to the local state
>
> `:onChange (fn [e] (om/set-state! component :local-state-key (-> e .-target .-value))`

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
                          :onChange (fn [e]
                                      (om/set-state! component :title (-> e .-target .-value)))
                          :placeholder "Session Title"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:speaker-name state)
                          :onChange (fn [e]
                                      (om/set-state! component :speaker-name (-> e .-target .-value)))
                          :placeholder "Speaker Name"})
          (dom/textarea #js {:className "form-control"
                             :value (:description state)
                             :onChange (fn [e]
                                         (om/set-state! component :description (-> e .-target .-value)))
                             :placeholder "Session Description"
                             :rows "5"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:speaker-biography state)
                          :onChange (fn [e]
                                      (om/set-state! component :speaker-biography (-> e .-target .-value)))
                          :placeholder "Speaker Biography"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:twitter-handle state)
                          :onChange (fn [e]
                                      (om/set-state! component :twitter-handle (-> e .-target .-value)))
                          :placeholder "Twitter Handle"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:github-handle state)
                          :onChange (fn [e]
                                      (om/set-state! component :github-handle (-> e .-target .-value)))
                          :placeholder "Github Handle"})
          (dom/input #js {:type "text"
                          :className "form-control"
                          :value (:speaker-website state)
                          :onChange (fn [e]
                                      (om/set-state! component :speaker-website (-> e .-target .-value)))
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
> React’s `onChange` event will fire as it changes, instead of after you finish changing it. Therefore onChange will fire each time you type a key or paste something.

Inside the onChange event, we call om/set-state!. This, as the name indicates, sets the state. We’ll see that in a minute, in more detail. We’re taking the event’s target (which is the dom element it relates to, in this case the input field) and getting its value.
