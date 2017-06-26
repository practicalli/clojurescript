# Om overview

## Om root

om.core/root establishes an Om rendering loop on a specific element in the DOM. 

`om.core/root` is idempotent (can be repeatedly called without affecting successive results). You may safely call it multiple times. 

Only one Om render loop is ever allowed on a particular DOM target.  You can of course create multiple DOM targets in an app with an Om root for each target.

`om.core/root` takes a function that creates a component, state in the form an associative data structure (map or vector) and the DOM element that defines where on the page the app is included.

`om.core/root` takes the following form:

```clj
(defn root
  ([f value options] ...))
```

`f` is a function returning an instance of IRender or IRenderState. f takes two arguments, a root cursor on the application state and the backing Om component for the root.

`value` is either a tree of associative ClojureScript data structures or an atom wrapping a tree of associative ClojureScript data structures.

`options` is a map containing any key allowed to `om.core/build`. Additionally the following keys are allowed/required:

* :target (required)

* :shared (optional) in order to provide global services

* :tx-listen a function that will listen in on transactions, should take 2 arguments:
a map containing the path, old and new state at path, old and new global state, and transaction tag if provided (:path, :old-value, :new-value, :old-state, :new-state and :tag).
the root cursor.

* :path to specify the path of the cursor into app-state (see #72)

* :instrument a function of three arguments that if provided will intercept all calls to om.core/build. The function arguments correspond exactly to the three argument arity of om.core/build


```clj
(om.core/root
  (fn [app-state owner]
    (reify
      om.core/IRender
      (render [_]
        (dom/h1 nil (:text app-state)))))
  {:text "Hello world!"}
  {:target (. js/document getElementById "my-app")})
```


## App-state atom

One of the cornerstones of an Om app is the app state atom. Every application has state. Any web app framework has to deal with it. In Om, we manage state with an atom. The atom points at the current state of the application, which is that little map there in the white box. And every time the state changes, the components need to be re-rendered.

In ClojureScript, we create an atom with a function called `atom`. The app state needs to be associative, which means either a map or a vector.

We’re going to be live reloading our code. Each time it loads, this line would redefine appstate to a new atom. We only want to load it once. So we use `defonce` instead of `def`.


## Render

If you want to put HTML into the page, you do so in render. We use the om.dom namespace to create dom nodes. There are functions there for any kind of HTML tag you need to create.

The first argument to each of them is always the HTML attributes, you know, the style, the class, all of the stuff that goes after the tag name in the HTML tag. We’ll see how to do those later. Just remember to putnil there for now to mean “no attributes”.

The rest of the arguments become the children (sub elements in the tree), and the tag is closed for you, if it needs to be. React knows which tags to close, so you don’t have to remember all of that.


