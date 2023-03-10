# Computer Move: Basic

Lets assume that the human player always goes first for now.

Once the human player has taken their turn, we will call a function for the computer to take their turn.

So we add a call to `computer-move` to the `:on-click` option of the `cell-empty` function.

```clojure
(defn cell-empty
  "Generate a cell that has not yet been clicked on"
  [x-cell y-cell]
  ^{:key (str x-cell y-cell)}
  [:rect {:width 0.9
          :height 0.9
          :fill "grey"
          :x x-cell
          :y y-cell
          :on-click
          (fn rectangle-click [e]
            (println "Cell" x-cell y-cell "was clicked!")
            (println
             (swap! app-state assoc-in [:board y-cell x-cell] :nought))
            (computer-move))}])
```

Then add the `computer-move` function

```clojure
(defn computer-move
  "Takes a turn for the computer, adding an X shape to the board"
  []
  (swap! app-state assoc-in [:board 0 0] :cross))
```

![Computer Move](/images/clojurescript-project-reagent-tictactoe--game-board--computer-move-basic.png)


> #### Hint:: Thinking time
> We could add some artificial thinking time to the computer move using `js/setTimeout`.  If you do set some thinking time, then you should also visualise that the computer is thinking, so the human player knows what is going on.
```clojure
(js/setTimeout (fn []) timeout)
```

![Computer thinking time - sample suggested code](/images/clojurescript-project-reagent-tictactoe--game-board--computer-move-thinking-time-suggestion.png)
