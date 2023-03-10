# Detecting Victory: REPL Experiments


## Find a winning row

To find a winning row we can compare the values in the vector with each other

```clojure
#_(apply = [:cross :cross :cross])
;; => true

#_(apply = [:nought :nought :nought])
;; => true

#_(apply = [:empty :cross :empty])
;; => false

#_(apply = [:cross :nought :empty])
;; => false
```

However, this approach also matches an :empty row or column

```clojure
#_(apply = [:empty :empty :empty])
;; => true
```

Using an anonymous function over the collection allows us to compare each value, if all values are not= :empty then we can return true

```clojure
(apply  (fn [cell-value] (not= :empty cell-value))[:empty :cross :cross])
```

As we will probably call this multiple times, lets convert it into a named function.

```clojure
(defn cell-empty?
  [cell-value] (not= :empty cell-value))
```

Hmm, still not idea, as any combination that does not contain :empty will return true

```clojure
(cell-empty? [[:cross :nought :cross]])
```

Applying both checks will give the right results

```clojure
(defn winning-line? [cell-row]
  (and
   (apply = cell-row)
   (apply cell-empty? cell-row)))

#_(winning-line? [:cross :cross :cross])
;; => true

#_(winning-line? [:nought :nought :nought])
;; => true

#_(winning-line? [:cross :nought :cross])
;; => false

#_(winning-line? [:empty :empty :empty])
;; => false

#_(winning-line? [:empty :nought :cross])
;; => false
```
