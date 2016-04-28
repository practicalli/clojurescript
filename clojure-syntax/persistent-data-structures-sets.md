# Theory: Sets

A Clojure set is a collection of unique values, unordered by default.

If you try and define a set with elements that are the same value, then a duplicate key error is returned.  This error can be seen when trying to define the following set

You want to create an unordered collection of distinct objects, which can be tested for membership quickly.

```
#{1 2 3 4 1}
```

The `set` function can be used to create a unique set from the another collection.  The `sorted-set` also created a unique set that is ordered by value

```
(set [1 2 3 4 1])

(sorted-set 1 4 0 2 9 3 5 3 0 2 7 6 5 5 3 8)
```


;; Set #{}
;; a unique set of elements



(#{:a :b :c} :c)
(#{:a :b :c} :z)




There are lots of functions that work on data structures

(def evil-empire #{"Palpatine" "Darth Vader" "Boba Fett" "Darth Tyranus"})

(contains? evil-empire "Darth Vader")

