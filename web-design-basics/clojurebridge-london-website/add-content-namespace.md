# Refactor content to its own namespace

Create a new namespace called `clojurebridge-landing-page.content` in the file `src/clojurebridge_landing_page/content.cljs`

Move all function definitions, except `landing-page` from the content section to the new file for the namespace.

## Require the `content` namespace

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

The landing page represents the order in which content sections are organised.

`level-separator` provides a named separation between each component.  The name is used by the navigation bar on the web page to jump to a specific content section on the page.

> Using the name on the separator ensures the top of the content section is not displayed under the navigation bar

```clojure
(defn landing-page []
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

The landing page should continue to work as before.  If not, ensure all files are saved and check if figwheel is showing errors on the bottom of the landing page.
