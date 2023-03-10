# Add Ring Dependency

As we are using the Ring library for our Clojure project we need to add that library as a dependency.  Just like other build tools (i.e. Maven, Gradle) we include this dependency in our build file, `project.clj`
  
> **Note** Edit the `project.clj` file and add the ring dependency.  For bonus points write a simple description of the project
    
```clojure
(defproject todo-list "0.1.0-SNAPSHOT"
  :description "A simple webapp using Ring"
  :url "http://example.com/FIXME"
  :license {:name "Eclipse Public License"
            :url "http://www.eclipse.org/legal/epl-v10.html"}
  :dependencies [[org.clojure/clojure "1.7.0"]
                 [ring "1.4.0"]])
```

> **Hint** Read the [dependencies secion of the Leiningen documentation](https://github.com/technomancy/leiningen/blob/stable/doc/TUTORIAL.md#dependencies) to learn more about adding libraries.

## Looking up Libraries & current versions

  There are a large number of Clojure libraries available via Clojars.org, an online repository similar to Maven Central.  
  
  To look up the latest version of a library, visit the Clojars.org website and search for the library name.


![](/images/clojure-webdev-clojars-ring.png)

  The dependency notation for Leiningen and Maven are documented for each library.
