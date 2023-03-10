# Interact with the REPL via your editor

> ####Hint::
> Your editor should either be running the Clojure/ClojureScript REPL's or connected to the REPLs run with `lein figwheel`

------------------------------------------

> ####Note::Edit welcome message
> Edit the message [:h3] in the `hello-world` component and see how it changes in the web browser
```clojure
(defn hello-world []
  [:div
   [:h1 (:text @app-state)]
   [:h3 "Edit this and watch it change!"]])
```

<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->
```clojure
(defn tictactoe-game []
  [:div
   [:h1 (:text @app-state)]
   [:p "Do you want to play a game?"]])
```

<!--endsec-->

------------------------------------------

> ####Note::Change the title by editing the `app-state`
> Change the :text message in `app-state` and see what happens in the browser
```clojure
(defonce app-state (atom {:text "Hello World"}))
```

<!--sec data-title="Reveal answer..." data-id="answer002" data-collapse=true ces-->

```clojure
(defonce app-state (atom {:text "Lets Play TicTacToe"}))
```

When you save a change to the `app-state` nothing happens in the browser.

As we use `defonce` rather than `def`, then Clojure does not update the definition if it already exists.  This prevents your app state from being cleared every time you save a change in your editor.

To see the change of a `defonce` you need to refresh your browser page.

<!--endsec-->
