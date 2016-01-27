# HTML Source Maps

When you have a highly interactive development environment set up with Clojure & Figwheel, the last thing you want to do is to try and pick through the JavaScript code and figure out which bit of Clojurescript is causing the problem.  With Source Maps you dont have to.

Source Maps allows you to see your Clojurescript code in the browser and see where your code is failing.

![Source Maps to help debugging your Clojurescript code](/images/clojurescript-source-maps-debugging.png)

You can set breakpoints in your Clojurescript code and they will appear in the source maps view in your browser.  You will also notice that the code is syntax highlighted, as browsers like Google Chrome support syntax highlighting directly (possibly through [CodeMirror](https://codemirror.net/))

## How source maps work

ClojureScript now supports HTML source maps so that you can debug ClojureScript directly in the browser, using the configuration option :source-map.

`:source-map` can be either a boolean, or if optimizations are enabled, a path to a file for the map.

If you are building using leiningen, the Clojurescript build section in `project.clj` would look like:

```
 :cljsbuild { 
    :builds [{:id "main"
              :source-paths ["src"]
              :compiler {
                :output-to "main.js"
                :output-dir "out"
                :optimizations :none
                :source-map true}}]})
```

After compilation, when you open an HTML file linking to the generated js file in your browser ensure that source maps are enabled via the Developer Tools settings.

For more details, see the [Clojure.org page on Source Maps](https://github.com/clojure/clojurescript/wiki/Source-maps)
