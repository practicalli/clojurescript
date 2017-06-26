# Add Cursor To Local State


> #### Note::Add Cursor to Local state so it can be modified


<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

```clj
    om/IInitState
    (init-state [this]
      {:title (:title cursor)
       :description (get cursor :description "")
       :speaker-name (get cursor :speaker-name "")
       :speaker-biography (get cursor :speaker-biography "")
       :twitter-handle (get cursor :twitter-handle "")
       :github-handle (get cursor :github-handle "")
       :speaker-website (get cursor :speakers-website "")}
```
<!--endsec-->


> #### Hint::
> The `get` function can return a default value if no value for an element is found in the collection the get function is applied to.
