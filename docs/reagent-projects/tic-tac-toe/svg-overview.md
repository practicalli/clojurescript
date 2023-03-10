# SVG Overview

You can draw SVG with different shapes, including rectangle `:rect`, circle.  To draw lines you can use `:path`

SVG objects are created using the same Hiccup style syntax as generating HTML, obviously with different tags.

Style options are added within a map `{}`.

```clojure
[:svg
  [:rect {:width 30
          :height 30
          :fill "blue"
          :stroke "red"
          :stroke-width 6}]]
```


A `:view-box` allows you to set your own unit of size within the SVG canvas

```clojure
[:center
  [:svg {:view-box "0 0 3 3"
         :width 500
         :height 500}
    [:rect {:width 0.9
            :height 0.9
            :fill "green"}]]]
```
