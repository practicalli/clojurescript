# Refactor welcome to a specific component

Rename the `landing-page` function to `welcome-message`.

Below the `welcome-message` function, create a new `landing-page` function definition as follows


```clojure
(defn landing-page []
  [welcome-message])
```

The `welcome-message` function needs to be defined above the `landing-page` function, as it `welcome-message` is call this new `landing-page` function.
