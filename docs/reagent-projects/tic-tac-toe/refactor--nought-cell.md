# Refactor: Nought Cell

A component to draw a cell containing a nought.

Using the SVG `:circle` we define a radius `:r` and decide what colour the circle should be `:fill`.

The `:stroke` is the line around the edge of the graphic, so by making the `:fill` colour the same as the background colour and having a `:stroke` of green gives a O shape rather than a solid circle.

The `cx` and `cy` options place the O shape in the center of the cell.

```clojure
(defn cell-nought
  "A cell with a nought inside it"
  [x-cell y-cell]
  ^{:key (str x-cell y-cell)}
  [:circle {:r 0.36
            :fill "white"
            :stroke "green"
            :stroke-width 0.1
            :cx (+ 0.42 x-cell)
            :cy (+ 0.42 y-cell)}])
```

> #### Hint::
> No need for an `:on-click` event for the nought component, as once it has been chosen in a game it should not change.
