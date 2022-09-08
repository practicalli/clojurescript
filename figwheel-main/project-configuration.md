# Project configuration

A new project is created in the `hello-world` directory and contains a `deps.edn` configuration

```clojure
 {:deps {org.clojure/clojure {:mvn/version "1.10.0"}
        org.clojure/clojurescript {:mvn/version "1.11.4"}
        cljsjs/react {:mvn/version "17.0.2-0"}
        cljsjs/react-dom {:mvn/version "17.0.2-0"}
        reagent/reagent {:mvn/version "1.1.1" }}
 :paths ["src" "resources"]
 :aliases {:fig {:extra-deps
                 {com.bhauman/rebel-readline-cljs {:mvn/version "0.1.4"}
                  org.slf4j/slf4j-nop {:mvn/version "1.7.30"}
                  com.bhauman/figwheel-main {:mvn/version "0.2.17"}}
                 :extra-paths ["target" "test"]}
           :build {:main-opts ["-m" "figwheel.main" "-b" "dev" "-r"]}
           :min   {:main-opts ["-m" "figwheel.main" "-O" "advanced" "-bo" "dev"]}
           :test  {:main-opts ["-m" "figwheel.main" "-co" "test.cljs.edn" "-m" "practicalli.test-runner"]}}}
```

Aliases were added by the template to run figwheel and build the ClojureScript code:

* `:fig` adds figwheel-main and rebel-readline libraries as dependencies, slf4j-nop provides a no-operation logger (suppresses default logger warning)
* `:build` runs figwheel-main which generates JavaScript from the ClojureScript code in the project
* `:min` creates a minified single JavaScript file for deployment
* `:test` runs all tests under `tests/practicalli` directory using the figwheel-main test-runner


`dev.cljs.edn` is the build configuration referred to by the `:build` and `:min` aliases using the `dev` name

```clojure
^{:watch-dirs ["test" "src"]
  :css-dirs ["resources/public/css"]
  :auto-testing true
   }
{:main practicalli.hello-world}
```

* `:watch-dirs` defines the directories to monitor files for saved changes
* `:css-dirs` defines the location of the CSS configuration
* `:auto-testng` to [automatically discover and run tests](https://figwheel.org/docs/testing.html)
* `:main` defines the main namespace for the application
