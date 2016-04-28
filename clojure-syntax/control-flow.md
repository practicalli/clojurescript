# Control Flow 



## If this then that, else the other

  Using the `if` funtion you can test if an expression evaluates to true.  If it is true, the first value is returned, if its false the second value is returned.
  
  Here is a simple example to see if one number is bigger that another

```clojure
(if (> 3 2) "Higher" "Lower")

=> "Higher"
```

```clojure
    (fn [x]
      (if (even? x)
        (inc x)
        (dec x)))
```

```
(doc if)
(doc if-not)
```

## When 

```clojure
    (when ( (when (> 3 2)
      (println "3 is greater than 2")
      "Higher")))

=> 3 is greater than 2
=> "Higher"
```
  You can use Lighttable to see the docs for a function by placing the cursor over the function name and pressing `Cntrl-d` - or search the Clojure docs in the command window 
```
(doc when)
(doc when-not)
```


## Conditional - Case 

```clojure
(case (inc 3)
         3 "Uh oh"
         4 "Yep!"
         "Not so sure...")
```
```
"Yep!"
```

```clojure
(cond
         (= 4 (inc 2)) "(inc 2) is 4"
         (= 4 (/ 8 2)) "Cond picks the first correct case"
	 (zero? (- (* 4 2) 8) "This is true, but we won't get here"
         :otherwise "None of the above."
```
```
"Cond picks the first correct case"
```

```
(doc cond)
(doc condp)
```
