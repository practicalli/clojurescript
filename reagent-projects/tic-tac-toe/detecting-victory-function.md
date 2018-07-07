# Detecting Victory: Function


```clojure
(defn cell-empty?
  [cell-value] (not= :empty cell-value))

```


```clojure
(defn winning-line? [cell-row]
  (and
   (apply = cell-row)
   (apply cell-empty? cell-row)))
```
