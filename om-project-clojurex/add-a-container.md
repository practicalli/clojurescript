# Add A Container

You may have noticed that the text on the web page is right up against the left hand side of the browser.  This doesnt look great.

> #### Note::Add div with a `container` style around our whole page
>
> Find or create a suitable `div` element and add the bootstrap className called `container`

<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

Add the container style to the top-most `div` element as follows:

```clj
(dom/div #js {:className "container"} 
  ,,,)
```

The most suitable div is the first one in the `render` function call of the `root-component` function.  This `div` effectively wraps the whole page.

```clj
(defn root-component [app owner]
  (reify
    om/IRender
    (render [_]
      (dom/div #js {:className "container"}
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

<hr/>

After applying the comtainer, there is now a margin around the content

![ClojureX Project - Adding a Container](/images/clojurex-project-mutliple-sessions-style-container.png)

> #### Hint::React Styles
> We are writing style in Clojurescript using maps, however we need to convert those styles to Javascript so that react can process them correctly.
>
> Om provides the `#js` macro that will convert our Clojurescript maps to the Javascript equivalents.
>
> `(dom/div #js {:className "bootstrap-style-name"})`
>
> To minimise the conversion, we use the Javascript naming convention for the style names, eg. className
>
> You could also put the container style in the `index.html` page, especially if you were to have multiple roots in your om project.
