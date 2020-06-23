# Refactor content to its own namespace

> #### TODO::work in progress, sorry

Create a new namespace called `clojurebridge-landing-page.content` in the file `src/clojurebridge_landing_page/content.cljs`

Move all function definitions, except `landing-page` from the content section to the new file for the namespace.

## require the `content` namespace

Edit the the file `src/clojurebridge_landing_page/core.cljs`.

Update the `clojurebridge-landing-page.core` namespace to require the new `clojurebridge-landing-page.content` namespace

The `content` namespace should be given the alias `content`

```clojure
(ns ^:figwheel-hooks clojurebridge-london-landing-page.core
  (:require
   [goog.dom :as gdom]
   [reagent.core :as reagent :refer [atom]]
   [clojurebridge-landing-page.content :as content]))
```

## Add the alias to the function calls


```clojure
(defn main-page []
  [:div
   [content/navigation-top]
   [content/banner-columns]
   [content/sponsor-current (get-in @app-state [:sponsors :current])]
   (content/level-separator "overview")
   [content/overview]
   (content/level-separator "showcase")
   [content/showcase]
   (content/level-separator "learning-paths")
   [content/learning-paths]
   (content/level-separator "install")
   [content/install]
   (content/level-separator "schedule")
   [content/schedule]
   (content/level-separator "resources")
   [content/resources]
   (content/level-separator "coaches")
   [content/coaches]
   (content/level-separator "sponsors")
   [content/sponsors]
   ])

```
