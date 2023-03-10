# Bulma CSS library

A simple and clean Cascading Style Sheet (CSS) library used to create professional looking websites.

Bulma is a CSS only framework (no JavaScript) that provides a range of easy to apply styles using meaningful style names.  Its quite lightweight and therefore fast to load along with your website.

Bulma is [compatible with all icon font libraries](https://bulma.io/documentation/elements/icon/), eg. Font Awesome, Material Design, Ionicons, etc.  Practicalli uses FontAwesome icon library to add common logos such at GitHub.

The Bulma library can be included via static html files, templates or via ClojureScript code.

> #### Hint::Use a Content Delivery Network
> [Bulma start documentation](https://bulma.io/documentation/overview/start/) shows how to use the Bulma library from a Content Deliver Network (CDN).  A CDN avoids the need to download and update a local copy of the Bulma CSS code.
>
> Downloading Bulma is only useful if editing or extending Bulma itself or need to use Bulma with a custom CSS or Sass development workflow (or there is a limited network connection)


## Including in static html file

Add Bulma CSS and FontAwesome icons to a Figwheel-main template project web page using a Content Deliver Network (CDN) hosted file

Edit the `resources/public/index.html` file

Add the following line of code inside the `<head>` tag:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css">
<script defer src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.0/css/all.min.css"></script>
```

The [Practicalli Landing page index.html file](https://github.com/practicalli/practicalli.github.io/blob/master/resources/public/index.html) is a complete example, including a totally unnecessary page loading indicator, as well as more useful JavaScript function to activate the Bulma CSS 'burger' menu displayed on smaller screens (tablets, smartphones, etc.).


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css">
    <script defer src="https://use.fontawesome.com/releases/v5.8.1/js/all.js"></script>
    <link href="css/style.css" rel="stylesheet" type="text/css">
    <link rel="icon" href="https://clojurescript.org/images/cljs-logo-icon-32.png">
    <!-- <link rel="stylesheet" href="css/debug.css" /> -->
  </head>
  <!-- Fix navigation menu to top of page -->
  <body class="has-navbar-fixed-top">
      <div id="app">
          <div class="container">
              <h1 class="title is-1">Loading the application, hold on tight!</h1>
              <!-- Totally redundant page loading progress indicator -->
              <progress class="progress is-large is-primary" max="100"></progress>
          </div>
      </div> <!-- end of app div -->
    <script src="cljs-out/dev-main.js" type="text/javascript"></script>

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
  </body>
</html>
```


## Bulma via Clojure Hiccup code

Generate html code from ClojureScript using the [hiccup style syntax](/hiccup-style-syntax.md).

```clojure
[:link {:rel "stylesheet"
        :href "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css"}]
[:script {:defer true
          :src "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.0/css/all.min.css"}]
```
