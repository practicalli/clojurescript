# Render Game Board

Generate the board from the data structure in @app-state.

Each cell of the board will be a coloured square (rectangle)

```clojure
(defn tictactoe-game []
  [:div
   [:div
    [:h1 (:text @app-state)]
    [:p "Do you want to play a game?"]]
   [:center
    [:svg {:view-box "0 0 3 3"
           :width 500
           :height 500}
     (for [x-cell (range (count (:board @app-state)))
           y-cell (range (count (:board @app-state)))]

       ^{:key (str x-cell y-cell)}

       [:rect {:width 0.9
               :height 0.9
               :fill "green"
               :x x-cell
               :y y-cell}])]]])
```

This is what the board should look like

![React TicTacToe - render game board](/images/clojurescript-project-reagent-tictactoe--render-board.png)
