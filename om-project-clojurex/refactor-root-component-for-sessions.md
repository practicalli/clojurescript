# Refactor Root Component for Multiple Sessions 

There are now multiple sessions in the data model, so lets refactor  that holds multiple sessions

> #### Note::Update `root-component` to display details from multiple session

> Add React DOM elements using `dom/div`, `dom/h2` and `dom/p`.
>
> See the [React DOM Elements](https://facebook.github.io/react/docs/dom-elements.html) documentation for more details.

> Assume the data you need is contained within the `app-state` which is passed as the argument `app` to the `root-component`.

<!--sec data-title="Reveal answer..." data-id="answer002" data-collapse=true ces-->

After the h1 for conference name, add a `div` element.  Inside this `div` the `for` function is used to iterate over the vector of sessions.  Each session creates a `h1` for `:title` and `p` for `:description` and `:twitter-handle`


```clj
(defn root-component [app owner]
  (reify
    om/IRender
    (render [_]
      (dom/div nil
        (dom/h1 nil (:conference-name app))
        (for [session (:sessions app)]
          (dom/div nil
            (dom/h1 nil (:title session))
            (dom/h3 nil (str "By " (:speaker-name session)))
            (dom/p nil (:description session))
            (dom/hr nil)
            (dom/p nil (str "About " (:speaker-name session) ":"))
            (dom/p nil (:speaker-biography session))
            (dom/p nil (:twitter-handle session))
            (dom/p nil (:github-handle session))
            (dom/p nil (:speakers-website session))))))))
```
<!--endsec-->


> #### Hint::
> Clojure can iterate over a collection using functions such as `for`
>
> Remember that React likes div tags around things too (as React does not render lists like list of DOM children)

<hr />

## Resulting web page

The web page with multiple sessions should look something like this:

![ClojureX Project - Multiple Sessions - no styles](/images/clojurex-project-multiple-sessions-no-styles.png)

