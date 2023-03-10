# Add Bulma CSS library

Bulma is a CSS only framework (no JavaScript) that provides a range of easy to apply styles using meaningful style names.  Its quite lightweight and therefore fast to load along with your website.

Bulma also recommends using FontAwesome library, to add common logos such at GitHub.

## Add Bulma CSS and FontAwesome icons to project web page

Edit the `resources/public/index.html` file in your project

Add the following line of code inside the `<head>` tag:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css">
<script defer src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.0/css/all.min.css"></script>
```

See the [Practicalli Landing page index.html file](https://github.com/practicalli/practicalli.github.io/blob/master/resources/public/index.html) for an example


## Bulma via Clojure Hiccup code

When using Clojure Hiccup code to generate the HTML page that loads the application (or any other HTML pages), Bulma CSS and FontAwesome can also be included using  the [hiccup style syntax](/hiccup-style-syntax.md).

```clojure
[:link {:rel "stylesheet"
        :href "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css"}]
[:script {:defer true
          :src "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.0/css/all.min.css"}]
```
