# Computer Move: REPL Experiments

Lets define a sample game board to work with, a board that is part way through a game should give us a good way to test computer moves

```clojure
(def game-board-example-mid-game
       [[:cross :nought :empty]
        [:empty :nought :empty]
        [:cross :nought :empty]])
```


## Iterate over the board

To make a move there needs to be an empty cell on the board to make a move in.

```clojure
(= :empty (get-in game-board-example-mid-game [1 0]))
;; => true

(= :empty (get-in game-board-example-mid-game [0 2]))
;; => true
```

lets get the co-ordinates for all the cells on the board that are empty, so we know which cells are available

```clojure
(for [row    (range board-dimension)
        column (range board-dimension)
        :when  (= :empty
                  (get-in game-board-example-mid-game [row column]))]
    [row column])
;; => ([0 2] [1 0] [1 2] [2 2])
```

We can use the same approach, but assigning it to a local name with let, so we can do more with the result

```clojure
(let [available-cells (for [row    (range 3)
                        column (range 3)
                        :when (= :empty
                                 (get-in game-board-example-mid-game [row column]))]
                    [row column])]
  available-cells)
;; => ([0 2] [1 0] [1 2] [2 2])
```


## Did we find any empty cells

We can check with the `empty?` function and therefore check if there are available cells by inverting the check with `not`

```clojure
(empty? '([0 2] [1 0] [1 2] [2 2]))

(not (empty? '([0 2] [1 0] [1 2] [2 2])))
```

However there is a Clojure idiom to use seq (mentioned in the docs for empty?)

```clojure
#_(seq '([0 2] [1 0] [1 2] [2 2]))
;; => ([0 2] [1 0] [1 2] [2 2])

#_(seq '())
;; => nil
```

So with seq if there are empty cells, those values are returned, otherwise `nil` is returned (which is falsey)


## Randomly selecting an available cell

To get one of the co-ordinates assuming there are available cells, we can use rand-nth

```clojure
#_(rand-nth '([0 2] [1 0] [1 2] [2 2]))
;; => [0 2]
```

Putting seq and rand-nth together we can get one of the available positions

```clojure
(def available-cells-example '([1 0] [0 2] [1 2] [2 2]))

(when (seq available-cells-example)
  (rand-nth available-cells-example))
;; => [1 2]
```

The computer can now make moves until no more cells are available

```clojure
(let [available-cells
       (for [row    (range board-dimension)
             column (range board-dimension)
             :when (=
                    :empty
                    (get-in game-board-example-mid-game [column row]))]
          [column row])

      next-move (when (seq available-cells)
                  (rand-nth available-cells))]

  (if next-move
    (str "update app-state")
    (str "display messages saying no more moves")))
;; => "update app-state"
```

Now we can fit this algorithm into our game code
