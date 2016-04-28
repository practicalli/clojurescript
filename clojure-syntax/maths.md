# Maths and numbers

  Doing some simple math helps you to get used to the structure of Clojure, espeicially the prefix notation.  Mathematics is also a good way to show how effective and clean prefix notation is.

```clojure
(+ 1 1 2489 459 2.) ; => 2
(- 2 1) ; => 1
(* 1 2) ; => 2
(/ 2 1) ; => 2
```

  Clojure uses Prefix notation, so math operations on many arguments is easy.

```clojure
(+ 1 2 3 4 5)

(+ 1 2 (* 3 4) (- 5 6 -7))

(apply + [1 2 3])

(map + [1 2 3.0] [4.0 5 6])

(repeat 4 9)
```

  Equality is represented by the `=` function.  Yes, `=` is a proper function too, not just an operator as with other languages.

```clojure
(= 1 1) ; => true
(= 2 1) ; => false
```

  Equality is very efficient when your data structures are immutable.  For example if you have very large data sets, you can simply compare a hash value to see if those data structures are the same.

  Of course you also have the `not` function for reversing logic too

```clojure
(not true) 

=> false
```


## Truethy experiments

;; some truthiness with math functions for you to try, as well as look at the types Clojure assigns

```clojure
(+)
(class (+))
(*)
(true? +)
(false? +)
(true? *)
(false? *)
(true? 1)
(true? -1)
(true? true)
(- 2)
; (class (/))  ;; wrong number of arguments error
```

Predicates - take a value and return a boolean result (true | false)
```clojure
(true? true)
(true? (not true))
(true? false)
(true? (not false))
(true? nil)
```

## Types

  Clojure uses Java's object types for booleans, strings and numbers.  Use the `class` function to inspect them.

```clojure
(class 1)
; Integer literals are java.lang.Long by default
(class 1.1)    ; Float literals are java.lang.Double

(class "")
; Strings always double-quoted, and are java.lang.String

(class false)  ; Booleans are java.lang.Boolean
(class nil)    ; The "null" value is called nil

(class (list 1 2 3 4))


(class true)
(class ())
(class (list 1 2 34 5))
(class (str 2 3 4 5))
(class (+ 22/7))
(class 5)
(class "fish")
(type [1 2 3])
(type {:a 1 :b 2})

(type (take 3 (range 10)))
```

## Ratios
  To help maintain the precision of numbers, Clojure has a type called Ratio.  So when you are dividing numbers you can keep the as a fraction using whole numbers, rather than constrain the result to a approximate

```clojure
(/ 2)
```

  A classic example is dividing 22 by 7 which is approximately the value of _Pi_

```clojure
(/ 22 7)

(class (/ 22 7))
```

If you want to force Clojure to evaluate this then you can specify one of the numbers with a decimal point

```clojure
(class (/ 22 7.0))
```


