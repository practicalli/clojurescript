# Designing the Game Board

Using the REPL we can experiment with different ways to model the game board.

## How to represent a cell

A cell is either going to be empty, or contain a nought or cross.  For simplicity, we will start with three keywords

```clojure
:empty
:nought
:cross
```

## Representing the whole board

We could just hard code the board as a vector of rows, with each row being a vector.  In this example we set all the board cells to `:empty`

```clojure
[[:empty :empty :empty]
   [:empty :empty :empty]
   [:empty :empty :empty]]
```

Generating a data structure to represet the game board

To create a row is simple to do using the repeat function to generate 3 :empty keywords and return them as a list

```eval-clojure
(repeat 3 :empty)
```

To make this a vector we can just wrap that in a vec function

```eval-clojure
(vec (repeat 3 :empty))
```

To create three rows we just repeat the code above 3 times

```eval-clojure
(vec (repeat 3 (vec (repeat 3 :empty))))
```

We can use the above code in a function and replace 3 with a local name that takes the value of the argument passed in so lets write a game-board function.


------------------------------------------

If you need a quick break while modeling your game board, here is a very silly distraction

{% youtube %}
https://youtu.be/0h9jN12QbdE
{% endyoutube %}
