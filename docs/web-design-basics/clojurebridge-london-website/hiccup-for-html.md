# Writing html in Clojure with hiccup

Rather than write `<div> </div>`, `<h1> </h1>`, `<p>  </p>` pairs of tags in html, we define our content using a syntax called hiccup.

A vector, `[]` is used to hold the name of the html tag, represented by a keyword such as `:div`

Defining our content in this way makes it easier to generate and transform using Clojure, so you can generate structure and content dynamically too.

For example this simple html code uses open and closing tags to define the scope of where to apply that tag.

```html
<div>
  <h1>Hello World</h1>
  <h3>Live reloading in the repl makes web development fun!</h3>
</div>
```

In Clojure, we only have the one tag, which is represented by a keyword that has the same name as the HTML tag.  The vector defines the scope of the tag.

Using vectors for scope its trivial to use structured editing to organise and refactor the structure of your web page content.


```clojure
(defn hello-world []
  [:div
   [:h1 (:text @app-state)]
   [:h3 "Live reloading in the repl makes web development fun!"]])
```

## Using state for dynamic content

We can also use dynamic information from the application state, defined as an atom called `app-state`.  As this name refers to an atom, we need to use the `@` character or the `deref` function to access its values

In this example, the atom contains a Clojure map with a key called `text`.  We can get the value associated with `text` in the map by de-referencing the atom.
```clojure
[:h1 (get @app-state :text)]
```

Its quite common to use the short form when the key of a map is the keyword type
```clojure
[:h1 (:text @app-state)]
```
