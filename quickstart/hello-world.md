# Hello World


Create a new file called `src/hello_world/core.cljs` and add the following code:

```clj
(ns hello-world.core)

(enable-console-print!)

(println "Hello world!")
```

* The first line declares the namespace, defining a named scope for our code.. Every ClojureScript file must declare a namespace and this namespace must match a path on disk. 

* The second line enables direct printing to the JavaScript `console` object in your browser 

* The third line is what should be a familiar print message.


