# Buttons

A button is created using the hiccup syntax.  A button is a type of input.

TODO: what are all the button options?


```clojure
(defn on-click-function []
  ,,,)

(defn reagent-component-funciton
 ,,,
  [:input {:type "button"
           :value "Thumbs Up!"
           :on-click (on-click-function)}]
```

When this button is clicked on the function `on-click` is called.

The `on-click` function should be called after the data you are creating or changing.


## :on-click in-line anonymous function

Instead of calling a named function, you can define an anonymous function.  The longer this anonymous function becomes, the more it should be changed to a named function.

```clojure
  [:input {:type "button"
   :value "Thumbs Up!"
   :on-click (fn [] ,,,) ])
```


Or using the syntax sugar for an anonymous function you can use `#()`

```clojure
  [:input {:type "button"
   :value "Thumbs Up!"
   :on-click #(,,,)])
```

> #### Hint:: Use syntax sugar and anonymous functions sparingly
> To keep the code as readable as possible, use named functions as the default approach for click handlers.
> If the on-click function is very short then its more acceptable to use an anonymous function instead.
