# Live reloading

figwheel-main provides live reloading of our application in the browser.  When we save a change to the code (ClojureScript or CSS), that change is automatically pushed to the browser and the web page is updates.

A ClojureScript logo will appear briefly in the corner of the web page to indicate an update is being pushed to the JavaScript engine in the browser.


## Edit the code to see live reloading

Edit the file `clojurebridge-landing-page/src/clojurebridge_landing_page/core.cljs`

Change the heading 3 contents in the `hello-world` function

```clojure
(defn hello-world []
  [:div
   [:h1 (:text @app-state)]
   [:h3 "Live reloading in the repl makes web development fun!"]])
```

The web page should have automatically updated

![ClojureScript project - live reloading website](/images/cljs-website-run--webpage-live-reloading.png)
