# Detecting Victory: Pattern matching REPL Experiments

A seemingly simple approach to detecting a winner is to use pattern matching.  Clojure also has the concept of destructuring, extracting values from a data structure based on a pattern.

The limitation with this approach is that more patterns need to be created if the size of the board changes


For a fixed 3x3 game board there are only 8 winning combinations, we could just create a pattern for each win. The patterns are the same for `:nought` and `:cross` we could just compare that each value is equal


## Define patterns for matching horizontal winning lines

```clojure
(def column-first
  [[cell-0 _ _]
   [cell-1 _ _]
   [cell-2 _ _]])

(def column-second
  [[_ cell-0 _]
   [_ cell-1 _]
   [_ cell-2 _]])

(def column-third
  [[_ _ cell-0]
   [_ _ cell-1]
   [_ _ cell-2]])


(defn check-winning-rows
  [board]
  (let [[[cell-0 _ _]
         [cell-1 _ _]
         [cell-2 _ _]]
        board]
    (if (= cell-0 cell-1 cell-2)
      cell-0
      false)))

(check-winning-rows [[:cross :cross :cross]
                     [:cross :cross :cross]
                     [:cross :cross :cross]])
;; => :cross

(check-winning-rows [[:cross :cross :nought]
                     [:nought :nought :cross]
                     [:cross :cross :nought]])
;; => false
```


## Pattern matching diagonals

```clojure
(= [:cross :cross :cross] [:cross :cross :cross])

(def board-of-crosses   [[:cross :cross :cross]
                         [:cross :cross :cross]
                         [:cross :cross :cross]])

(def board-of-stalemate [[:cross :cross :nought]
                         [:nought :nought :cross]
                         [:cross :cross :nought]])

(=  [[:cross :cross :cross] [:cross :cross :cross] [:cross :cross :cross]]
    [[:cross :cross :cross] [:cross :cross :cross] [:cross :cross :cross]])
;; => true

(=  [[:cross :cross :cross] [:cross :cross :cross] [:cross :cross :cross]]
    [[:cross :cross :cross] [:cross :cross :cross] [:cross :cross :nought]])
;; => true
```


## Pattern matching using destructuring

Using destructuring we can just look at the values we are interested in

The let destructuring pattern pulls out the values for the diagonal line, from top left to bottom right

```clojure
(let [[[cell-00 _ _][_ cell-11 _][_ _ cell-22]] board-of-crosses]
  (= cell-00 cell-11 cell-22))
;; => true

(let [[[cell-00 _ _][_ cell-11 _][_ _ cell-22]] board-of-stalemate]
  (println cell-00 ":" cell-11 ":" cell-22)
  (= cell-00 cell-11 cell-22))
;; => false
```


Not sure naming these patterns with a def is that useful
Not this way, as its not correct clojure (names are not defined)

Should create two functions instead

```clojure
#_(def diagonal-row--top-left-to-bottom-right
  [[cell-00 _ _]
   [_ cell-11 _]
   [_ _ cell-22]])

#_(def diagonal-row--top-right-to-bottom-left
  [[_ _ cell-02]
   [_ cell-11 _]
   [cell-20_ _]])
```
