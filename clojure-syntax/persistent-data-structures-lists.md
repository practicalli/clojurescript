# Theory: Lists

List is a general set of elements with a sequential lookup time.  New elements are added to the front of the list as this is the most efficient way to update a list.

You can use the list function to create a new list (try the following expressions in a REPL)

```
(list 1 2 3 4)
(list )    ;; creates an empty list
(list 1 2 "three" [4] five '(6 7 8 9))
(list -1 -0.234 0 1.3 8/5 3.1415926)
(list "cat" "dog" "rabit" "fish" 12 22/7)
(list :cat :dog :rabit :fish)
```

You can mix types because Clojure is dynamic and it will work it out later, you can even have functions as elements, because a function always returns a value.  In the following example we define a list that includes a function call to the `str` function that joins its parameters into a single string.

```
(list :cat 1 "fish" 22/7 (str "fish" "n" "chips"))
```

## Lists evaluate as function calls

One unique thing about lists is that the first element is always evaluated as a function call, with the remaining elements as arguments.  So, defining a list just using `()` will cause an error

```
(1 2 3 4)   ;; failing expression
```

The previous list definition fails because there is no function defined with the name `1`

We can call any of our own functions or any functions from Clojure using a list

```
(str "The str function" " " "joins strings together")
(+ 1 2 3 4 5)  ;; + is a function that adds numbers
(apply * [2 4 6])  ;; applies the * function to each element in the collection
```

## Treat lists as data

There is a special function called `quote` that tells Clojure to treat all the elements of the list as data.  You can also use the short-hand quote character, **'**

```
(quote (1 2 3 4))

'(1 2 3 4)
```

So using the quote character we can define lists very easily and concisely.

```'
'(-1 -0.234 0 1.3 8/5 3.1415926)
'("cat" "dog" "rabit" "fish")
'(:cat :dog :rabit :fish)
'(:cat 1 "fish" 22/7 (str "fish" "n" "chips"))
```


## Duplicate elements in a list 

A list can contain elements that are the same value.

```
(list 1 2 3 4 1)
(list "one" "two" "one")
(list :fred :barney :fred)
```

If you wish to ensure only unique values then you can use a [set](sets.html)

## Changing lists with the cons function

As we have seen in the introduction to this section, changing a lists values once created is not possible.  However when a list is used as the paramter to a function call it can return a new list with different values.

The `cons` function is used to add values to the list

```
(cons 5 '(1 2 3 4))

;; => (5 1 2 3 4)
```

You will notice that the value 5 is added to the front of the new list that is returned.  As this is a linked list and not indexed, it is more performant to add values to the front of a list.

Here is another example with strings

```
(cons "fish" '("and" "chips"))
```

