# Computer Move: Random Available Cell


```clojure
(defn computer-move
  "Takes a turn for the computer, adding an X shape to the board"
  []
  (let [available-cells
        (for [row    (range board-dimension)
              column (range board-dimension)
              :when (=
                     :empty
                     (get-in (@app-state :board) [column row]))]
          [column row])

        next-move (when (seq available-cells)
                    (rand-nth available-cells))]

    (if next-move
      (do
        (prn "Computer move at:" next-move)
        (swap! app-state assoc-in [:board (first next-move) (second next-move)] :cross))
      (prn "Computer move: no more moves available"))))
```


> #### Hint::
> If there are no more moves left, then a message could be displayed on the web page, so the user knows (although as the cells are all full, then its kind of implied)
