# React Unique Index

> #### Info::Reference
> [Redit: How to use reagent in ClojureScript for Iterating](https://www.reddit.com/r/Clojure/comments/3vc50b/how_to_use_reagent_in_clojurescript_for_iterating/)

When we render the game board in [React.js](https://reactjs.org/) it really wants a unique index for every cell in the grid of cells.

## Warning in browser
In the Developer console of the browser, you see the following error:

Every element in a sequence should have a unique key

[![React warning - child in array must have unique index](/images/chrome-devtools-console--react--waringing-array-children-unique-key.png)](/images/chrome-devtools-console--react--waringing-array-children-unique-key.png)


## What React.js is looking for

When we render the game board in React.js we use the following generated data structure

```clojure
([:rect {:width 0.9, :height 0.9, :fill "purple", :x 0, :y 0}]
 [:rect {:width 0.9, :height 0.9, :fill "purple", :x 0, :y 1}]
 [:rect {:width 0.9, :height 0.9, :fill "purple", :x 0, :y 2}]
 [:rect {:width 0.9, :height 0.9, :fill "purple", :x 1, :y 0}]
 [:rect {:width 0.9, :height 0.9, :fill "purple", :x 1, :y 1}]
 [:rect {:width 0.9, :height 0.9, :fill "purple", :x 1, :y 2}]
 [:rect {:width 0.9, :height 0.9, :fill "purple", :x 2, :y 0}]
 [:rect {:width 0.9, :height 0.9, :fill "purple", :x 2, :y 1}]
 [:rect {:width 0.9, :height 0.9, :fill "purple", :x 2, :y 2}])
```

For the developer we can see that combining the `:x` and `:y` co-ordinates would provide an implied index, React.js is looking for something implicit.

## Adding Meta data to each cell

To fix this issue, we add a piece of metadata to each cell in the game board by combining the `:x` and `:y` co-ordinates into a single value.

```clojure
^{:key (str x-cell y-cell)}
```


So when we iterate through the game board using the `for` function, we generate a unique metadata :key for each cell, ie. 00, 01, 02, etc

```clojure
(for [x-cell (range (count (:board @app-state)))
      y-cell (range (count (:board @app-state)))]

     ^{:key (str x-cell y-cell)})

     )
```
