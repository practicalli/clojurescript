# Component Game Board

Now we have experiment with the board design, lets put our results into a component.

```lisp
(defn game-board
  "Create a data structure to represent the values of cells in the game board.
  A vector is used to hold the overall game board
  Each nested vector represents a line of the game board.
  Dimension specifies the size of the game board."
  [dimension]
  (vec (repeat dimension (vec (repeat dimension :empty)))))
```

Lets create a default dimension for the board (width & height)

As the game board is square, we only use one value for height and width


```lisp
(def board-dimension 3)

```

Update the `app-state` so that it doesn't get over-written on reload


```lisp
(defonce app-state
           (atom
             {:page
               {:title "Lets Play TicTacToe"
                :message "Do you want to play a game?"}
              :board
                (game-board board-dimension)}))
```
