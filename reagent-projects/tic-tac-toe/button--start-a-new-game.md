# Button: Start a new game

Add a button to the `tictactoe-game` component to start a new game.

The button resets the board by updating the `app-state`.  The current `app-state :board` is swapped with a new game board with all the values set to `:empty`.


```clojure
(defn tictactoe-game []
  [:div
   [:div
    [:h1 (:text @app-state)]
    [:p "Do you want to play a game?"]]

   [:button {:on-click (fn new-game-click [e]
                           (swap! app-state assoc :board (game-board board-dimension)))}
    "Start a new game"]

   [:center
    [:svg {:view-box "0 0 3 3"
           :width 500
           :height 500}
     (for [x-cell (range (count (:board @app-state)))
           y-cell (range (count (:board @app-state)))]
       (case (get-in @app-state [:board y-cell x-cell])
         :empty [cell-empty x-cell y-cell]
         :cross [cell-cross x-cell y-cell]
         :nought [cell-nought x-cell y-cell]))]]])
```
