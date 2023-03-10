# Tic-tac-toe: Create project
Create the project using the figwheel-main template to quickly create a working configuration.  The template can be used with Clojure CLI tools or Leiningen

The project will include the reagent library as a dependency, along with code for a working reagent application.


{% tabs deps="deps.edn projects", lein="Leiningnen projects" %}

{% content "deps" %}
Use the `:project/new` alias from [`practicalli/clojure-deps-edn`]({{ book.P9IClojureDepsEdnInstall }}) to create a new Clojure CLI tools project, using the figwheel-main template.

```clojure
clojure -M:project/new figwheel-main practicalli/tictactoe -- --reagent
```

The output of the command should look similar to this:

![ClojureScript new project using figwheel-main template for tictactoe](/images/clojurescript-project-new-figwheel-main-tictactoe-output.png)


## deps.edn configuration
The template creates a project `deps.edn` configuration.

The aliases section includes the figwheel-main and rebel-readline-cljs libraries.  This has been renamed from `:fig` to `:figwheel`.

The aliases section also has 3 different build configurations, each of which runs figwheel with a specific configuration.  One of these aliases should be used with the `:figwheel` alias.

* `:build` is the development build of the project and runs a rebel readline REPL
* `:minify` (renamed from `:min`) generates a single javascript file for deployment, using advanced deployment
* `:test-runner` (renamed from `:test`) will run unit tests and show a test report in the browser


```clojure
{:paths ["src" "resources"]

 :deps
 {org.clojure/clojure       {:mvn/version "1.10.0"}
  org.clojure/clojurescript {:mvn/version "1.10.773"}
  reagent                   {:mvn/version "0.10.0" }}

 :aliases
 {:figwheel
  {:extra-deps
   {com.bhauman/rebel-readline-cljs {:mvn/version "0.1.4"}
    com.bhauman/figwheel-main       {:mvn/version "0.2.11"}}
   :extra-paths ["target" "test"]}

  ;; build configurations
  :build
  {:main-opts ["-m" "figwheel.main" "-b" "dev" "-r"]}

  :minify
  {:main-opts ["-m" "figwheel.main" "-O" "advanced" "-bo" "dev"]}

  :test-runner
  {:main-opts ["-m" "figwheel.main" "-co" "test.cljs.edn" "-m" "practicalli.test-runner"]}

  } ;; End of aliases
 }  ;; End of deps.edn
```


## Starting the development build
Open a terminal window in the root of the tictactoe projects and run the `clojure` command with the `:figwheel` and `:build` aliases

```shell
clojure -M:figwheel:build
```

<!-- TODO: show output of repl and browser web page automatically added. -->


## Starting the unit test runner
Open a terminal window in the root of the tictactoe projects and run the `clojure` command with the `:figwheel` and `:test-runner` aliases

```shell
clojure -M:figwheel:test-runner
```


<!-- TODO: show test runner results in browser tab -->


{% content "lein" %}

 Use Leiningen build tool to create a new Clojurescript project, using the figwheel-main template.

```clojure
lein new figwheel practicalli.tictactoe -- --reagent
```

[![Create project with leiningen: tic-tac-toe-reagent](/images/clojurescript-project-reagent-tictactoe--create-project-with-figwheel-template.png)](/images/clojurescript-project-reagent-tictactoe--create-project-with-figwheel-template.png)


{% endtabs %}



## Project structure

The project created should have the following files and directories

[![Project structure for tic-tac-toe-reagent](/images/clojurescript-project-new-figwheel-main-tictactoe-directory-structure.png)](/images/clojurescript-project-new-figwheel-main-tictactoe-directory-structure.png)

<!-- [![Project structure for tic-tac-toe-reagent](/images/clojurescript-project-reagent-tictactoe--new-project-tree-structure.png)](/images/clojurescript-project-reagent-tictactoe--new-project-tree-structure.png) -->

You can use any command line or graphical file browser to view the project structure.
