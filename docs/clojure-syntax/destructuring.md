# Destructuring

Destructuring is a powerful way to get data from a collection using positional or key based pattern matching.

In our examples We are using the `let` function to create local bindings (labeling data with a specific name).  The let function has two arguments, the first is the name to be used for the binding and the second argument is the value the name will be assigned to.

When the value passed to the `let` function is a collection, you can use destructuring to do the assignments.

**Example 1:**
Here we have data in a vector (an array like collection) and we want one or more names to reference the individual elements.

```clojure
(let [[a b c & d :as e] [1 2 3 4 5 6 7]]
  [a b c d e])
```

The let function creates the local names `a`, `b`, `c`, `d` and `e`.  The names a to d take the corresponding positional value in the collection: a is bound to 1, b is bound to 2, etc.

The `:as` keyword tells the `let` function to bind everything else remaining to `e`.


**Example 2:**
We now have a nested collection, a vector that contains two vectors.  We can still use positional destructuring to pull out the values into names

```clojure
(let [[[x1 y1][x2 y2]] [[1 2] [3 4]]]
  [x1 y1 x2 y2])
```

**Example 3:**
This distructuring also works with strings

```clojure
(let [[a b & c :as str] "asdjhhfdas"]
  [a b c str])
```

**Example 4**
And finally destructuring with maps.  Here we are also using the `:or` directive to set a default value if there is no match.

```clojure
(let [{a :a, b :b, c :c, :as m :or {a 2 b 3}}  {:a 5 :c 6}]
  [a b c m])
```

It is often the case that you will want to bind same-named symbols to the map keys. The :keys directive allows you to avoid the redundancy:

```clojure
(let [{fred :fred ethel :ethel lucy :lucy} m] )
```
 can be factored to:

```clojure
(let [{:keys [fred ethel lucy]} m] )
```
