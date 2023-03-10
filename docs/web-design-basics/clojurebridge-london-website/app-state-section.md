# App State driven section

The sponsor section of the website will change the sponsor details each time we have a new event.  Rather than _hard code_ the sponsor details, we can add them to the application state.  Then each time we have a new event, all we need to do is update that state with new sponsor details.

Update the map to contain a `:sponsors` key whose value is a map.

That map containes `:current` and `:past` sponsors (past sponsors will be a map that has the number of the event and the sponsor details copied from the :current map).

```clojure
(defonce
  app-state
    (atom
      {:text "Hello world!"
       :sponsors
         {:current
           {:name    "Functional Works"
            :logo    "images/functional-works-logo.svg"
            :website "https://functional.works-hub.com/"
            :message "Breaking down the barriers to hiring the right software engineers,
            providing a platform to managing the whole process (written in ClojureScript)."}
          :past    {:9 {,,,}}}}))
```

Here is an example of a current sponsor component.

```clojure
(defn sponsor-current
  "Sponsors for our current event, to help that sponsor get some exposure

  Argument: hash-map of strings - :name, :website, :logo, :message"
  [sponsor-details]
  [:div {:class "container"}
   [:div {:class "box"}
    [:div {:class "column is-half is-8 is-offset-2"}
     [:a {:href (get sponsor-details :website)}
      [:h3 {:class "title is-5 has-text-centered"} (str "Our Sponsors:" " " (get sponsor-details :name))]]
     [:div {:class "columns"}
      [:div {:class "column"}
       [:figure {:class "image"}
        [:a {:href (get sponsor-details :website)}
         [:img {:src "images/functional-works-logo.png"}]]]]
      [:div {:class "column"}
       [:div {:class "content"}
        [:p (get sponsor-details :message)]]]]]]])
```
