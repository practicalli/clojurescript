# Configure main namespace

> **Note** Set the default namespace for your Clojure project.

Edit the `project.clj` file and add `:main todo-list.core` configuration option.

Setting the default namespace will automatically call a function called `-main` when the Clojure project is run, i.e. via `lein run`

```clojure 
(defproject todo-list "0.1.0-SNAPSHOT"
  :description "A simple webapp using Ring"
  :url "http://example.com/FIXME"
  :license {:name "Eclipse Public License"
            :url "http://www.eclipse.org/legal/epl-v10.html"}
  :dependencies [[org.clojure/clojure "1.7.0"]
                 [ring "1.4.0"]]
  :main todo-list.core)
```

  Now you are ready to run your web server.

