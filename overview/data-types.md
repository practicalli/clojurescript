# Basic values 

Although you typically do not define types in Clojure (like you would do in Object Oriented languges) there are types underneath and Clojure decides on the most appropriate types to use for any given values.

You can coerce a value to a particular type, typically when you are passing values to the host language (i.e Java / Javascript types)

## Numbers

Integer and decimal numbers are supported


```clojure
1 2 3 4 5 6.0
```

##  Ratios

From mathematics, a ratio is a relationship between two numbers indicating how many times the first number contains the second.  In Clojure it also means that when dividing two or more integer numbers the value can be kept as a ratio if otherwise a decimal (real) number would be returned.

```clojure
(/ 22 7.0)
(/ 5 20)

(/ (* 22/7 3) 3)
```
Ratios delay the need to drop into decimal numbers.  Once you create a decimal number then everything it touches had a greater potential to becoming a decimal


## Strings 

Strings are defined using double quotes

```clojure
"This is a string"
"Strings are immutable too"
```

## Symbols and binding 

The names we give functions and data structures to have an easy way to refer to them 

```clojure
(def name "value")
(def name (fn [paramter] (behaviour)))

(let [name "value"])
```

## Keywords 

Used for [enumerations](http://en.wikipedia.org/wiki/Enumeration) and as keys in maps (a map is a series of zero or more key value pairs)


## Collections

There are four very special collections as part of the Clojure core, all immutable and referred to as [persistent data structures](persistent-data-structures.html)

* List - a sequentially accessed linked list.  The first element of a list is evaluated as a function call (unless a quote character is placed in front of the list)

* Map - a key value pair collection, typically known as a hash maps

* Vector - an array like structure in that it is indexed and fast for random access

* Set - a unique set of elements, which can be ordered but are not by default

See the section on [persistent data structures](persistent-data-structures.html) for more details.
