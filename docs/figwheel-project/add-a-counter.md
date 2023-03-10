# Add a counter


Let's create a simple program for demonstration purposes. This is going to be a bare bones program that uses the [sablono](https://github.com/r0man/sablono) ClojureScript interface to React.js.

First add `[sablono "0.3.6"]` to the `:dependencies` list in your `project.clj`.

You will need to restart Figwheel to pick up the new dependency.

> ##### Pro-tip: use `lein clean`
> Whenever you add new dependencies and restart Figwheel, also run `lein clean`. It will reduce the 
> chances of working with old code

Add a place for us to mount our app in your `index.html`.

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <div id="app"></div> <!-- add this line -->
    <script src="main.js" type="text/javascript"></script>
  </body>
</html>
```
Now, edit your `src/hello_seymore/core.cljs` file:

```clojure
(ns hello-seymore.core
  (:require [sablono.core :as sab]))

(def app-state (atom { :likes 0 }))

(defn like-seymore [data]
  (sab/html [:div
             [:h1 "Seymore's quantified popularity: " (:likes @data)]
             [:div [:a {:href "#"
                        :onClick #(swap! data update-in [:likes] inc)}
                    "Thumbs up"]]]))

(defn render! []
  (.render js/React
           (like-seymore app-state)
           (.getElementById js/document "app")))

(add-watch app-state :on-change (fn [_ _ _ _] (render!)))

(render!)
```

Since Figwheel is running, once you save this file you should see the application running in the browser.

Let's talk about the reloadability of this tiny React app.

First, try the program out by clicking the **Thumbs up** link several times.  You will see Seymore's popularity increase. Popularity should really be measured by how many times people are willing to click a thumbs up eh?

Now, if you change the source files by simply adding a blank line and saving it (something I actually do pretty often), the code will reload and you will see the popularity count go to zero. This is because we are redefining the `app-state` atom on every code load.  This is not what we want. You can fix this by using `defonce` instead of `def` on `app-state` as follows:

```clojure
(defonce app-state (atom {:likes 0}))
```

After you make this change you will see that the state of the program will persist through reloads.

Something else to notice is that the call to `add-watch` is getting called over and over again on reload. But this is OK because it is just **replacing** the current `:on-change` listener, making this top level side-effect reloadable.

Also, you will notice that we have a top level call to `render!` at the end of the file. This forces a re-render every time the file is loaded. This is helpful so that we will render app changes as we edit the file.

Remove the `like-seymore` function from the `core.cljs` file and add it to its own file `src/hello_symore/components.cljs`.

Updated `core.cljs`:
```clojure
(ns hello-seymore.core
  (:require [sablono.core :as sab]
            [hello-seymore.components :refer [like-seymore]]))

(defonce app-state (atom { :likes 0 }))

(defn render! []
  (.render js/React
           (like-seymore app-state)
           (.getElementById js/document "app")))

(add-watch app-state :on-change (fn [_ _ _ _] (render!)))

(render!)
```

New `src/hello_seymore/components.cljs`:
```clojure
(ns hello-seymore.components
  (:require [sablono.core :as sab]))

(defn like-seymore [data]
  (sab/html [:div
             [:h1 "Seymore's quantified popularity: " (:likes @data)]
             [:div [:a {:href "#"
                        :onClick #(swap! data update-in [:likes] inc)}
                    "Thumbs up"]]]))
```

As long as Figwheel was running this whole time your refactor should have been live loaded into the browser. After reflecting on the coolness of this, go ahead and edit the `components.cljs` file and remove the word "quantified" and save it. You will see your changes show up as expected.
