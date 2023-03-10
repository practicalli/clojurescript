# Using Figwheel


If you are new to Figwheel here is a [Quick Start](https://github.com/bhauman/lein-figwheel/wiki/Quick-Start) tutorial. Working through this Quick Start will probably save you a tremendous amount of time.

## Usage

Make sure you have the [latest version of leiningen installed](https://github.com/technomancy/leiningen#installation).

Then include the following `:dependencies` in your `project.clj` file.

```clojure
[org.clojure/clojure "1.7.0"]
[org.clojure/clojurescript "1.7.170"]
```

Then include `lein-figwheel` in the `:plugins`
section of your project.clj.

```clojure
[lein-figwheel "0.5.0-3"]
```
