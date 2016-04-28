# Add a webserver

Use the Ring Library to create the simplest possible web server, one that will simply return a message regardless of the web page we ask for.

![Ring - Adaptor and anonymous function](../images/clojure-ring-adaptor-anonymous-function.png)
  
## Including Ring in the namespace 
  
First make the ring library functions accessible in the namespace.  Using `:require` we can add one or more libraries to our namespace.  We can also use the `:as` keyword to specify a short-hand way of refering to a library.

> **Note** Delete all the code in `src/todo_list/core.clj` and replace it with the following code, adding the ring adaptor for Jetty to our project.

```clojure
(ns todo-list.core
  (:require [ring.adapter.jetty :as jetty]))
```

This expression defines the current namespace as `todo-list.core`, providing a scope for all the functions and data structures we define within it.

The `:require` expression makes the `ring.adaptor.jetty` namespace accessible within the `todo-list.core` namespace.  We can now call any of the public functions in the `ring.adaptor.jetty` namespace.  We defined an alias called `jetty` so to call the `run-jetty` function we use `jetty/run-jetty` rather than the fully qualified namespace of `ring.adaptor.jetty/run-jetty` 

You can specify any valid Clojure name for a namespace alias, however please consider the readability of your code and choose a meaningful alias.  Later in the workshop we will show other options for including functions from other namespaces.

## Add a main function to run Jetty

> **Note**  Add a function called `-main` to the  `src/todo_list/core.clj` file.

> The `-main` function takes a port number as an argument which we pass when running the application.  The Ring Jetty adaptor is used to run an instance of Jetty.  The `-main` function contains an anonymous function (lambda) that takes any request and returns a _response map_.

A response map contains the following key / value pairs
  * `:status` - the result of the request, eg. 200 OK, 401 Not Found, etc 
  * `:body` - the content to be returned (web page, json, etc)
  * `:headers` - a map of standard headers included in any web browser response 

```clojure
(defn -main
  "A very simple web server using Ring & Jetty"
  [port-number]
  (jetty/run-jetty
     (fn [request] {:status 200
                   :body "<h1>Hello, Clojure World</h1>  <p>Welcome to your first Clojure app.  This message is returned regardless of the request, sorry</p>"
                   :headers {}})
     {:port (Integer. port-number)}))
``` 

> **Hint** Using a `-` at the start of the `-main` function is a naming convention, helping you see which function is the entry point to your program.  Leiningen also looks for this -main function by default when running your application.

>  The `Integer.` function is a call to `java.lang.Integer`.  The `.` is a special form that tells Clojure to treat this name as a call to Java.  See [coersing types and java.lang](coersing-types-and-java-lang.html)

> The `jetty/run-jetty` function takes two arguments.  In our example, the first argument is an anonymous function that returns a map (the response to the browser request);  the second argument is a port number to run the jetty server on expressed as a Java Integer object.

<hr />

## The complete code for the web server 

  The code in `src/todo_list/core.clj` should now look like this:
  
```clojure
(ns todo-list.core
  (:require [ring.adapter.jetty :as jetty]))

(defn -main
  "A very simple web server using Ring & Jetty"
  [port-number]
  (jetty/run-jetty
     (fn [request] {:status 200
                   :body "<h1>Hello, Clojure World</h1>  <p>Welcome to your first Clojure app.  This message is returned regardless of the request, sorry<p>"
                   :headers {}})
     {:port (Integer. port-number)}))
```

