# Create A Conference Title

Our project already has application state, bound to the name `app-state`.

```clojure
(defonce app-state (atom {:text "Hello Chestnut"}))
```

> #### Note::Refactor app-state to hold a conference name
> Create a key called `:conference`
>
> Add a value as a string that holds the tile of the conference
>
> The `:title` key is no longer needed in our state.

<!--sec data-title="Reveal answer..." data-id="answer00" data-collapse=true ces-->

```clojure
(defonce app-state (atom {:conference-name "ClojureX"}))
```

Saving the file with this change will update the text on the website.

<!--endsec-->
