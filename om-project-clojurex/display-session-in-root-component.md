# Add Session to root-component

The `root-component` currently displays the title from the `app-state` via the `render` function.

```clj
(defn root-component [app owner]
  (reify
    om/IRender
    (render [_]
      (dom/div nil (dom/h1 nil (:text app))))))
```

We have a data model for our sessions and sample data, so lets add some of that session data the page.

> #### Note::Add a single session to our root-component

> Use the session data we previously created to test the new version of the `root-component`

<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

Add a `div` element inside the first `div`, after the `h1` element.  In the new `div` add a paragraph element that will display the string extracted via `:session` `:title` from the app-state

```clj
(defn root-component [app owner]
  (reify
    om/IRender
    (render [_]
      (dom/div nil
               (dom/h1 nil (:conference-name app))
               (dom/div nil (:title (:session app)))))))
```

Saving the file with the code above show no additional information on the web page.  So now add a session to the state using the `swap!` function

```clj
(swap! app-state assoc :session {:title "Opening Keynote"})
```
Or using the `john` name we bound to our session previously, adding the full session information to the app-state

```clj
(swap! app-state assoc :session john)
```

<!--endsec-->

> #### Hint::
> React is very happy when you wrap elements in a `div` element.  If an element is not displaying, it may need to be wrapped in a div.


## Using `reify` to check the React API is implemented

reify is built-in to Clojure and ClojureScript. It’s easy: you give it some protocols and it makes an object that satisfies those protocols.

Each protocol has a number of methods, maybe one, maybe more. You tell reify which protocol to implement, then follow it by the method implementations.

Om builds components that implement its lifecycle protocols. The Om lifecycle closely follows the underlying React lifecycle methods. It’s complex, but luckily you only need to know a few to get started–just the most common and important ones.

Right now, we only need `om/IRender`.  Later we’ll use `om/IInitState`.
