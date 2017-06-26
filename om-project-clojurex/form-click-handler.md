# Form Click Handler

Our form doesn’t do anything, but because we know about cursors, we can now add a click handler to our Save button.

> #### Note::Add an :onClick handler for the form button
>
> call `preventDefault` on the event to prevent React from updating the state after each keypress in the form.  The state should only update when we press the Submit button.
> 
> Add some dummy data in the form, or just press Submit to see a new session appear.


<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

```clj
(defn session-add [cursor component]
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
                      "Save"))))))
```

<!--endsec-->

> #### Hint::
> You can double check the form is working by evaluating the `@app-state` in the REPL or your editor
>
> `fnil` is a function that let’s you define a default behaviour when the argument is nil.  So if the session data is nil in the above example, then we conjoin the empty vector
