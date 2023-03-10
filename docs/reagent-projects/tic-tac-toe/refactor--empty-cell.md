# Refactor: Empty Cell


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
             (swap! app-state assoc-in [:board y-cell x-cell] :cross)))}])
```
