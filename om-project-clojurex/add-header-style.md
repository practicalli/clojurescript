# Add Header Style

To make our conference name standout, we are going to add a style.  In Bootstrap a common header style is called **Jumbotron**


> #### Note::Add the Jumbotron style to the heading
> Edit the `src/clojurex/cljs/core.cljs` file and update the `root-component` to include the `jumbotron` style for the conference name
>
> Include any additional `div` elements if neccessary

<!--sec data-title="Reveal answer..." data-id="answer00" data-collapse=true ces-->

The `jumbotron` style can be added to the `h1` element that displays the conference name:

```clj
(dom/h1 #js {:className "jumbotron"} (:conference-name app))
```

If the heading is going to contain more than one dom element, then you would introduce a new `div` element with the `jumbotron` style.  This new `div` element would contain the `h1` element and any others for the heading.

```clj
(dom/div #js {:className "jumbotron"}
  (dom/h1 (:conference-name app)))
```

<!--endsec-->


Take a look at your page and the heading should stand out much more.

![ClojureX Project - Bootstrap jumbotron](/images/clojurex-project-bootstrap-jumbotron.png)

