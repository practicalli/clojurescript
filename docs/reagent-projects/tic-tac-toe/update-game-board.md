# Update Game Board

When we click on a cell with the mouse we want to change that cell to be a nought or cross (depending on which side we are playing).

To change a cell we add an `:on-click` event to each cell in the board game.  The `:on-click` event is an option on the `[rect ,,,]` that defines the cell.

In this example we just change the `app-state` to `:clicked` and add some basic debugging so we can see the results in the developer console.

```clojure
 :on-click
   (fn rectangle-click [e]
     (println "Cell" x-cell y-cell "was clicked!")
     (println
       (swap! app-state assoc-in [:board y-cell x-cell] :clicked)))}])]]])
```


We could add a simple if condition to determine which colour to fill the cell

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
               :fill (if (= :empty (get-in @app-state [:board y-cell x-cell]))
                       "green"
                       "purple")
               :x x-cell
               :y y-cell
               :on-click
               (fn rectangle-click [e]
                 (println "Cell" x-cell y-cell "was clicked!")
                 (println
                  (swap! app-state assoc-in [:board y-cell x-cell] :clicked)))}])]]])
```
