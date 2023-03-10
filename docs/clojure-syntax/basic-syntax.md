# Basic Syntax

Clojure has a really small syntax, probably the smallest readable syntax ever create.  The core primitives that make up the language are:

![Clojure primitives](/images/clojure-primitives-common.png)

There are a few primitives added for host language interop too.  Everything else is either a function or occasionally a [macro](http://clojure.org/reference/macros).


# Clojure syntax - brackets everywhere

  Clojure is percieved as having an abundance of `()`, the symbols that represent a list.  
  
  As Clojure is a LISP (List Processing) language then everything is written in the form of a list.  This makes Clojure very powerful and also easier to read.

  Using a list structure also demonstrates the data-centric nature of Clojure.  Every item in the list has a value, with the first item evaluated by a function call.

> **Comment** The seemingly abundance of `()` does put some people off until they realise there are fewer "special characters" in Clojure than in other C-based langauges (Java, C#, C, etc).  A good editor will also match brackets for you as you type, making it easy to write Clojure.

> Syntax differences seem a very trivial reason to avoid learning Clojure.  Any Clojure or Lisp aware editor will significantly reduce your typing and errors due to missing delimiters (ie. no more errors due to missing ; in C-based languages)


## Prefix notation

  Instead of having a mix of notations like in many other languages, Clojure uses pre-fix notation entirely.

  In Clojure operators are applied uniformly and there is no room for ambiguity:
```clojure
    (+ 1 2 3 5 8 13 21)
    (+ 1 2 (- 4 1) 5 (* 2 4) 13 (/ 42 2))
    (str "Clojure" " uses " "prefix notation")
```
  In Java and other C-based languages you have to explicitly add operators everywhere and there can be a mixture of notations

```java
    (1 + 2 + 3 + 5 + 8 + 13 + 21);
    (1 + 2 + (- 4 1) + 5 + (* 2 4) + 13 + (/ 42 2));
    StringBuffer mystring = new StringBuffer("C-based languages" + " mix " + "notation");
    x+=1; 
    x++; 
    x--; 
    x+=y; 
    x-=y; 
    x*=y; 
    x/=y;
```


## Extending the language with macros

A [macro](http://clojure.org/reference/macros) is a way to reduce boilerplate by wrapping up common code into a much simpler expression.  For example the the `defn` macro acts like any other function, but as it is a macro it is first expanded to the code structure it represents and then evaluated.

See the [Macros section on Clojure.org] for more information.  Other good introductions to macros include

* [Clojure from the ground up: macros](https://aphyr.com/posts/305-clojure-from-the-ground-up-macros)
* [Clojure for the brave and true: Macros](http://www.braveclojure.com/read-and-eval/#Macros)

> **Hint** As anyone developer can create macros, the language can grow and evolve without having to wait for the language designers or official releases.  Macros are something you will use as functions, it is rare that you will write your own macros unless you are building a new kind of library or framework.
