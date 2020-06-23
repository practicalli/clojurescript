# Create a Clojurebridge London website

> ####Info::This section is new, so feedback is appreciated

We have a very [simple website for ClojureBridge London](https://clojurebridgelondon.github.io/) and we would like to know how to make it easier to use.

We would also like to have a website create with Clojure or preferably ClojureScript, so we can host the website on GitHub pages.

> ####HINT::An example ClojureScript website using Bootstrap CSS library
> [Clojure Study Group project](https://github.com/practicalli/clojure-study-group-website) contains examples of code you can include to create your ClojureScript website

## Create a ClojureScript project

> ####Note:: Create a ClojureScript website for ClojureBridge London
>
> Create a project using the figwheel template, adding reagent library.
>
```shell
lein new figwheel clojurebridge-website -- --reagent
```

This will create a project with a working web page (usually described as a single page app).


## Add Bootstrap CSS library

Bootstrap is a simple way to structure and make your website more appealing, using a wide range of CSS styles available.

> ####Note::Add Bootstrap to project web page
> Edit the `resources/public/index.html` file in your project
> Add the following line of code inside the `<head>` tag:
```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/css/bootstrap.min.css" integrity="sha384-GJzZqFGwb1QTTN6wy59ffF1BuGJpLSa9DkKMp0DgiMDm4iYMj70gZWKYbI706tWS" crossorigin="anonymous">
```

See the [Clojure study group index.html](https://github.com/practicalli/clojure-study-group-website/blob/master/resources/public/index.html fs) file for an example

The [Bootstrap Introduction documentation](https://getbootstrap.com/docs/4.2/getting-started/introduction/) includes examples of layouts and component styles you can include in your website.


## Adding sections to the website

Create a function for each section of the website you want to add.

> ####HINT::Reagent examples
> [Introduction to Reagent](https://reagent-project.github.io/) has many simple examples of functions you can include in the website
>
> [Guide to Reagent](https://purelyfunctional.tv/guide/reagent/) has even more examples

#### Create a banner heading using Bootstrap jumbotron style

```clojure
(defn website-title []
  [:div {:class "jumbotron practicalli-jumbotron"}
   [:h1 (get-in @app-state [:website :title])]
   [:h4 (get-in @app-state [:website :description])]])
```

## Writing html in Clojure with hiccup

Rather than write `<div> </div>`, `<h1> </h1>`, `<p>  </p>` pairs of tags in html, we define our content using a syntax called hiccup.

A vector, `[]` is used to hold the name of the html tag, represented by a keyword such as `:div`

Defining our content in this way makes it easier to generate and transform using Clojure, so you can generate structure and content dynamically too.


## References
* [Reagent Mysteries - part 1: vectors and sequences](https://presumably.de/reagent-mysteries-part-1-vectors-and-sequences.html)
* [SVG in reagent](https://www.mattgreer.org/articles/embedding-svg-into-a-reagent-component/)
