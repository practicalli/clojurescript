# Strings in Clojure 

  While you can use the Java-like function `println`, this is refered to as a side-effect because when you call this function it returns nil.  The actual text is output to the REPL or console.
  
  Here is a very simple xeample

```clojure
(println "Hello, whats different with me?  What value do I return")

=> "Hello, whats different with me"
=> nil
```

  In Clojure, you are more likely to use the `str` function when working with strings.

```clojure  
(str "Hello, I am returned as a value of this expression")

=> Hello, I am returned as a value of this expression
```

  You can see that there are no side-effects when using `str` and the string is returned as the value of the function call.
  
  Its easy to join strings together with the `str` function

```clojure
(str "Hello" ", " "HackTheTower UK")

=> Hello, HackTheTower UK
```
