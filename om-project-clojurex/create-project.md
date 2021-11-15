# Create the project

Create the project using the Leiningen Chestnut template

```
lein new chestnut om-clojurex
```

Lets quickly explore the key parts of this project

## Dependencies

> #### Note::Review Project Dependencies

> Open the `om-clojurex/project.clj` file to review the dependencies already added to the project.

```clojure
  :dependencies [[org.clojure/clojure "1.8.0"]
                 [org.clojure/clojurescript "1.9.89" :scope "provided"]
                 [com.cognitect/transit-clj "0.8.285"]
                 [ring "1.4.0"]
                 [ring/ring-defaults "0.2.0"]
                 [bk/ring-gzip "0.1.1"]
                 [ring.middleware.logger "0.5.0"]
                 [compojure "1.5.0"]
                 [environ "1.0.3"]
                 [org.omcljs/om "1.0.0-alpha36"]]
```

* `org.clojure/clojure` - provides the Clojure language and tooling
* `org.clojure/clojurescript` - adds the Clojurescript compiler
* `ring` libraries & `compojure` - server-side requests & routing
* `com.cognitect/transit-clj` - convey values between Clojure & Javascript
* `environ` - manage environment settings
* `org.omcljs/om` - a React API based micro-framework


## Namespace Libraries

> #### Note::Review the Namespace
> Open the `om-clojure/src/om-clojurex/cljs/core.cljs` file to see how the namespace and required libraries are defined in the sample code.

The Om libraries are included in the namespace with `:require`, giving the libraries aliases.

```clojure
(ns om-clojurex.core
  (:require [om.core :as om :include-macros true]
            [om.dom :as dom :include-macros true]))
```

* `om.core` - functions that model the React API, such a `render` and `root`
* `om.dom` - create html code from Clojure code

## Om State & Components

> #### Note::Review the definitions for the state and the component and root functions
> Open the `om-clojure/src/om-clojurex/cljs/core.cljs` file to review the sample code provided with the project.

* Enable printing of messages to the browsers javascript console log

```clojure
(enable-console-print!)
```

* Define the application state (the model) for the application.  This is a map (hash map with key value pairs) that contains a single key called `:text` and a string as its value.

```clojure
(defonce app-state (atom {:text "Hello Chestnut!"}))
```

> #### Hint::def or defonce
> The `defonce` function is used to prevent the app-state being reset to the default value every time a change is saved to the file.  This enables you to evolve the code and state at the same time.


* Define a component that returns a div element, containing an h1 element which contains a string taken from the `:text` part of the application state.

```clojure
(defn root-component [app owner]
  (reify
    om/IRender
    (render [_]
      (dom/div nil (dom/h1 nil (:text app))))))
```


* Define the root of the Clojurescript project and define where it will be included in the main html page.  The root contains one component, to which is passed the app-state

```clojure
(om/root
 root-component
 app-state
 {:target (js/document.getElementById "app")})
```

> #### Hint::Connecting the app with the html page
> The "app" refers to a div with the same id in the main html file


## Main HTML source code file

> #### Note::Review the HTML page
> Open the `om-clojure/resources/public/index.html` file to review the sample HTML code provided with the project.

* In the body of the HTML file is a `div` tag which defines where the generated Javascript code is to be included on the page.

```clojure
  <body>
    <div id="app"></div>
    <script src="js/compiled/om_clojurex.js" type="text/javascript"></script>
  </body>
```
