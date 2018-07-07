# Reagent Design: Manage App State

State changes are an unavoidable in an user interface (UI).  A UI wouldnt be much good if it didnt change and show you new information.

An Atom is used manage state changes in Reagent, specifically the Atom from the Reggent library

Unlike most things in Clojure, an Atom is mutable.  This means that when you use a function to change the atom, the contents of that atom really changes.

## Game state

The state of the game changes as the players take turns.  The squares on the board will change state from containing nothing, a nought or a cross.

## Why use an Atom?  Isnt mutable state bad?

Clojure developers minimise the use of mutable state where possible.  However in a user interface, state needs to change (or your user interface never changes).

Atoms provide a simple way for developers to manage mutable state, ensuring that only one part of a program can change the atom at any point in time.  So you do not need to manage concurrency and threads for an atom, making your code very simple.


## Atoms dont make their contents mutable

Just because an Atom is mutable, doesnt mean the data inside the atom is mutable.  For example, if you put a vector of 3 numbers in an atom and then call a function to add a 4th number, the original vector is not changed, simply replaced by a new copy of that vector containing 4 numbers.

So you are still working with immutable data, its just convieniently held in a mutable container so its easy to change.


## Using defonce over def

We are using `defonce` rather than def to stop the value of the atom being reloaded every time we make a change to our code.

Using `def` instead, then every time we saved our code our app-state would be reset back to the initial values.

```cljs
(defonce app-state (atom {:text "Hello world!"}))
```

> #### Hint:: Manual app-state reset
> If you manually reload the page of your application in the browser then the `app-state` will be set back to its initial value.


<hr />

> #### Hint:: Atom Vs Reagent Atom
> The Reagent library automatically watches Reagent atoms for changes and will automatically update any components using data in those atoms.
>
> The Clojure language has a built-in atom type which does a similar job to the Reagent Atom, however you need to write your own code to watch for changes to get the same results at Regent.
