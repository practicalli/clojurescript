# Theory: Vectors

Clojure Vectors can be though of as array collections.  The vector is

* indexed so you can get fast random access
* immutable - a persistent data structure

Vectors and maps are the most common data structures use to hold data in Clojure

You can use the vector function to create a new vector

```
(vector 1 2 3 4)
```

Usually you just use the [] notation to create a vector to help keep your code readable

```
[1 2 3 4]
[1 2.4 3.1435893 11/4 5.0 6 7]
[:cat :dog :rabit :fish]
[:cat 1 "fish" 22/7 (str "fish" "n" "chips")]
[]
```

You can also put other data structures in vectors, in this example a list is an element of the vector

```
[1 2 3 '(4 5 6)]
```

Remember we defined five earlier in the code

```
[1 2 3 4 (list five)]
```

## Duplicate elements

A vector can hold duplicate values, which makes vectors a great default data structure for any kind of values.

```
[1 2 3 4 1]
```

## Types

```
(class [1 2 3])

(coll? [1 2 3]) ; => true

(seq? [1 2 3]) ; => false
```

# Using Vectors

Clojure uses dynamic typing, this means its trivial to mix and match different kinds of data.

Here we are defining a name for a vector, which contains numbers, a string and name of another def.

```
(def my-data [1 2 3 "frog" person])

my-data
```

You can also dynamically re-define a name to points to a different value

```
(def my-data [1 2 3 4 5 "frog" person])
```

The original value that defined my-data remains unchanged (its immutable), so anything using that value remains unaffected.  Essentially we are re-mapping my-data to a new value.



```
(def developer-events-vector
  [:devoxxuk :devoxxfr :devoxx :hackthetower] )
```

Lets define a simple data structure for stocks data.  This is a vector of maps, as there will be one or more company stocks to track.  Each map represents the stock information for a company.

```
(def portfolio [ { :ticker "CRM" :lastTrade 233.12 :open 230.66}
                 { :ticker "AAPL" :lastTrade 203.25 :open 204.50}
                 { :ticker "MSFT" :lastTrade 29.12  :open 29.08 }
                 { :ticker "ORCL" :lastTrade 21.90  :open 21.83 }])
```

We can get the value of the whole data structure by refering to it by name

```
portfolio
```

As the data structure is a vector (ie. array like) then we can ask for a specific element by its position in the array using the nth function

;; Lets get the map that is the first element (again as a vector has array-like properties, the first element is referenced by zero)

```
(nth portfolio 0)
```

The vector has 4 elements, so we can access the last element by referencing the vector using 3

```
(nth portfolio 3)
```

As portfolio is a collection (list, vector, map, set), also known as a sequence, then we can use a number of functions that provide common ways of getting data from a data structure

```
(first portfolio)
(rest portfolio)
(last portfolio)
```


You can pull out data from a Vector
([1 2 3] 1)

([1 2 3] 1 2)  ;; wrong number of arguments, vectors behaving as a function expect one parameter
