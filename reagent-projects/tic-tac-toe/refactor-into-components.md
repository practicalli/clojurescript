# Refactor Into Components

Keep the `tictactoe-game` component fairly simple by creating functions to generate the graphics for different cells.


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
       (case (get-in @app-state [:board y-cell x-cell])
         :empty [cell-empty x-cell y-cell]
         :cross [cell-cross x-cell y-cell]
         :nought [cell-nought x-cell y-cell]))]]])
```
