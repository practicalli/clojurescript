# Create Form Component

> #### Note::Create a new component for a more generic form
> Move `IInitState` and `init-state` from the `session-add` component to the `form component`
>
> Move the `render-state` to the `form` component

<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

```clj
(defn form [cursor component options]
  (reify
    om/IInitState
    (init-state [this]
      {:title (:title cursor)
       :description (get cursor :description "")
       :speaker-name (get cursor :speaker-name "")
       :speaker-biography (get cursor :speaker-biography "")
       :twitter-handle (get cursor :twitter-handle "")
       :github-handle (get cursor :github-handle "")
       :speaker-website (get cursor :speakers-website "")}))
```
<!--endsec-->


> #### Hint::

