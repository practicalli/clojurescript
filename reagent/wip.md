# Work In Progress


## Do not deref inside lazy sequences

Hey, any idea why this doesn't work? Clicking on the button doesn't update the component

```clojure
(defn root-component []
  (let [selected (r/atom 0)]
    (fn []
      [:p [:button {:on-click #(reset! selected 1)} "Click me"]
       (map
         (fn [x] (str (= x @selected)))
         [0 1 2])])))

```
However, this works and update the component correctly:


```clojure
(defn root-component []
  (let [selected (r/atom 0)]
    (fn []
      [:p [:button {:on-click #(reset! selected 1)} "Click me"]
       (str (map
              (fn [x] (= x @selected))
              [0 1 2]))])))
```

(note the difference of where I put the str function)

dereferencing the selected atom inside of a lazy sequence, so reagent isn’t able to capture the dereference and set up its tracking magic for you
if you lift the dereference out of the map you should see it work:

```clojure
(defn root-component []
  (let [selected (r/atom 0)]
    (fn []
      [:p [:button {:on-click #(reset! selected 1)} "Click me"]
       (let [selected-val @selected]
         (map
           (fn [x] (str (= x selected-val)))
           [0 1 2])]))))
```
