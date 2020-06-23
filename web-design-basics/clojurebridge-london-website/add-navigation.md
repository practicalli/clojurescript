# Add Navigation bar

To jump to specific content, we will add a navigation bar at the top of the page.

The navigation will be fixed in place, so it will not move as the page is scrolled.

The navigation will be responsive, so when the website is viewed on smaller screens, the navigation will show as a drop-down button (referred to as a burger as that is the rough shape of the icon typically used).



## Navigation section

Create a function to define the navigation, using the `navbar` class from Bulma.


```clojure
(defn navigation-top
  "A responsive navigation that is fixed to the top of the page"
  []

  [:nav {:class      "navbar is-fixed-top is-dark"
         :role       "navigation"
         :aria-label "main navigation"}
   [:div {:class "container"}
    [:div {:class "navbar-brand"}
     [:a {:class "navbar-item"
          :href  "/"}
      [:img {:src "images/clojurebridge-logo.png"}]]
     [:span {:class       "navbar-burger burger"
             :data-target "navbarClojureBridge"}
      ;; Empty spans needed for navbar burger
      [:span][:span][:span]]]

    [:div {:id    "navbarClojureBridge"
           :class "navbar-menu"}
     [:div {:class "navbar-start"}
      [:a {:class "navbar-item"
           :href  "#overview"} "Overview"]
      [:a {:class "navbar-item"
           :href  "#showcase"} "Showcase"]
      [:a {:class "navbar-item"
           :href  "#learning-paths"} "Learning Paths"]
      [:a {:class "navbar-item"
           :href  "#schedule"} "Schedule"]
      [:a {:class "navbar-item"
           :href  "#install"} "Install"]
      [:a {:class "navbar-item"
           :href  "#resources"} "Resources"]
      [:a {:class "navbar-item"
           :href  "#resources"} "Coaches"]
      [:a {:class "navbar-item"
           :href  "#sponsors"} "Sponsors"]

      [:span {:class "navbar-item"}
       [:a {:class  "button is-inverted"
            :target "_blank"
            :href   "https://github.com/ClojureBridgeLondon/landing-page-draft"}
        [:span {:class "icon"}
         [:i {:class "fab fa-github"}]]
        [:span "Issues/PRs"]]]]]]]
  )
```


## Fixing spacing under navbar

To prevent hiding content under the navigation bar, we add the `has-navbar-fixed-top` class to the body of the `index.html` file

```html
  <body class="has-navbar-fixed-top">
```


## Script to populate the drop-down menu

As Bulma does not have any JavaScript functionality, we need to add a script to dynamically populate the navigation bar drop-down menu when on smaller devices.

```html
    <!-- Script for Bulma hamburger menu -->
    <!-- https://www.adam-bray.com/2018/04/03/responsive-bulma-css-navigation-bar/ -->
    <script>
     (function() {
         var burger = document.querySelector('.burger');
         var nav = document.querySelector('#'+burger.dataset.target);

         burger.addEventListener('click', function(){
             burger.classList.toggle('is-active');
             nav.classList.toggle('is-active');
         });
     })();
    </script>
```

> #### TODO::
> The script is the approach that Bulma suggests.  However, it should be possible to write ClojureScript to do this work.  This JavaScript would then be removed.
>
> One approach is to make the navigation data part of the application state, then it can be easily used and updated.  Using the application state helps make the webpage layout more dynamic, as changes to the application state will cause parts of the website to be re-drawn (re-rendered).
