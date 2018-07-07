# Refactor: Cross Cell

A component to draw a cell containing a cross.

As there is not a cross shape in SVG, we use two SVG `:line` to create an X shape.  Each line defines its start and end co-ordinates, `:x1 :y1 , :x2 :y2`.  To make this a single image we group the lines together with `:g`

As the shape is made up of two lines, then the colour is defined just with `:stroke`.  We set `:stroke-linecap` to `round` so the ends of each line has a nice round shape.

Rather than use `cx` and `cy` options place the two lines in the center of the cell, we set a `:transform` to move the X shape into the center.


```clojure
(defn cell-cross
  "A cell with a cross inside it"
[x-cell y-cell]
  ^{:key (str x-cell y-cell)}
  [:g {:stroke "purple"
       :stroke-width 0.4
       :stroke-linecap "round"
       :transform
       (str "translate(" (+ 0.42 x-cell) "," (+ 0.42 y-cell) ") "
            "scale(0.3)")}
   [:line {:x1 -1 :y1 -1 :x2 1 :y2 1}]
   [:line {:x1 1 :y1 -1 :x2 -1 :y2 1}]])
```
