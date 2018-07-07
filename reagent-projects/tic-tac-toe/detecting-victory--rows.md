# Dectecting Victory - rows only

A function that will test to see if a row has a winning line

```clojure
(defn winning-row
  "Return the winner, :nought or :cross if there is a winning row, otherwise return false"
  [cell-row]
  (if (and (apply = cell-row)
           (apply #(not= :empty %) cell-row))
    (first cell-row)
    false))
```

Lets add something simple to check if the first row is a winner

```clojure
(defn check-for-winner
  "Checks the app-state to see if there is a current winner"
  []
  (let [winner (winning-row (first (@app-state :board)))]
    (prn "The winner is:" winner)
    winner))
```

Now lest update check-for-winner to try all rows.  We will assume that there will be only one winning row.
