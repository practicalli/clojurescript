# Interacting with the REPL

With a running REPL you can make changes instantly.

Place your browser where you can see both it and the editor / repl you are using to make changes.  Then you can see just how fast Clojurescript development is.

If all is well you now have a browser window saying 'Hello Chestnut', and a REPL prompt that looks like **cljs.user=>**.


## Make changes from the REPL

Quickly experiment with your app by entering Clojurescript code into the repl.

> #### Note::Use the REPL to change the message in the browser window

> Enter the following lines of code in the REPL:

```clojure
(in-ns conference-reagent.core)

(swap! app-state assoc :text "I feel the power of the REPL")
```

The first line changes the namespace to `conference-reagent.core`, giving you access to the functions and definitions of our project.

The second line updates a value in the application data model, `app-state`.  Specifically this line runs the `assoc` function to update the value pointed to by `text` in the map that is referred to by the name `app-state`.  The `swap` function is used as the map is defined as an `atom`, a mutable container, providing a managed way to update the state.

> #### Hint::

> Atoms are covered in more detail in section ..., you dont need to understand them just yet.

## Make changes in the Clojurescript file

Make more permanent changes by editing the file and saving the changes.

> #### Note::Change files in the Project & watch the saved changes update the browser

> Make the following changes to the CSS styles and main Clojurescript file, to see how quickly your changes are reloaded.

1. Open `resources/public/css/style.css` and change some styling of the H1 element. Notice how it's updated instantly in the browser.

2. Open `src/cljs/conference-reagent/core.cljs`, and change `dom/h1` to `dom/h2`. As soon as you save the file, your browser is updated.

3. Open `src/cljs/conference-reagent/core.cljs` and add the following code:
```clojure
(swap! app-state assoc :text "Updates from the Editor")
```
Evaluate this line of code and again to see how the browser updates.
