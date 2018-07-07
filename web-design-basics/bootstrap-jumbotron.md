# Bootstrap: Jumbotron

Jumbotron is a simple banner style header to the web page.

Use this in your main component to help draw the page

We wrap the jumbotron in a bootstrap container (see previous section)

```clojure
(defn conference [app-state]
  [:div {:className "container"}
   [:div {:className "jumbotron"}
    [:h1 (:conference-name app-state)]
    [:h2 (:community app-state)]
    [:h3 (:slogan app-state)]]])
```

![Bootstrap Jumbotron: ClojureX example](/images/web-design-bootstrap-jumbotron-clojurex.png)


## Jumbotron styles

Inline or added to local styles.css
