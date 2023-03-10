![ClojureScript Figwheel-main and Reagent banner](https://raw.githubusercontent.com/practicalli/graphic-design/live/banners/clojuresript-figwheel-reagent.png)

Adding `reagent` to the project is a common way to create react.js style applications, usually to create a Single Page App (SPA).  Rum and Om-next are other libraries that are used for the same type of app.

The figwheel-main template takes several options, one of which defines if react, rum or om is added to a project.

{% tabs deps="Clojure CLI project", lein="Leiningen project" %}

{% content "deps" %}
Create a Clojure CLI tools `deps.edn` project using the `:project/new` alias from [practicalli/clojure-deps-edn]({{ book.P9IClojureDepsEdnInstall }})  configuration, including the `--reagent` template option which adds a common library for reactive web page development

Run this command in a terminal window

```shell
clojure -X:project/new :template figwheel-main :name practicalli/landing-page :args '["--reagent"]'

```

> The older form of the command to create a project is `clojure -M:project/new figwheel-main practicalli/landing-page -- --reagent`

The command will create a new directory with the project name and include the reagent library and sample code to form a simple react-style application.

<!-- ![Command line: run ClojureScript REPL with Figwheel-main and rebel readline](/images/clojurescript-project-new-figwheel-main.png) -->


{% content "lein" %}
Create a Leiningen `project.clj` project using the following command, including `--reagent` which is a common library for reactive web page development

```shell
lein new figwheel-main practicalli/landing-page -- --reagent
```

{% endtabs %}


## Run a ClojureScript project
Run the ClojureScript project from the command line initially to ensure that everything is working.

The project will start a REPL and figwheel-main will launch a connected browser REPL in the default web browser.

In the terminal window used to create the project, change into the project directory

```shell
cd landing-page
```

{% tabs depsrepl="Clojure CLI project", leinrepl="Leiningen project" %}

{% content "depsrepl" %}
Use the Clojure CLI tools to run the project using the `:fig` alias and the `:build` build task.

Also use `:repl/rebel` alias from [practicalli/clojure-deps-edn]({{ book.P9IClojureDepsEdnInstall }}) to run the ClojureScript REPL with rebel readline for a richer REPL experience.  Using the `:repl/rebel` alias before `:fig` adds the rebel-readline library dependency


```shell
clojure -M:repl/rebel:fig:build
```

![Command line: run ClojureScript REPL with Figwheel-main and rebel readline](/images/clojurescript-project-repl-start-terminal-rebel.png)



{% content "leinrepl" %}

Use Leiningen to run the ClojureScript project using the `:fig` alias and the `:build` build task.

```shell
lein fig:build
```


{% endtabs %}

A window or tab should automatically open once the project starts.  This takes a few moments, so take a few deep breaths.


![ClojureScript project with Figwheel-main and rebel readline - default webpage](/images/clojurescript-project-figwheel-reagent-webpage-default.png)


## Check the browser connection
Check the browser REPL is connected by evaluating a ClojureScript expression in the ClojureScript REPL.

First create a simple altert in the browser window using JavaScript interoperability

In the terminal at the ClojureScript REPL prompt, swap in a new value into `app-state`

```clojure
(js/alert "Hello from the ClojureScript REPL")
```

Another interesting test is to update the live state of the application. The web page title is generated from the project state, held in an atom called `app-state`.  If the value held by `app-state` is updated, then the page should automatically update.

In the terminal at the ClojureScript REPL prompt, require the `practicalli.landing-page` namespace to load the ClojureScript code.  Then switch in to the `practicalli.landing-page` namespace and finally swap a new value into the `app-state`

```clojure
(require 'practicalli.landing-page)
(in-ns 'practicalli.landing-page)
(swap! app-state assoc :text "Hello from the REPL")
```

![ClojureScript REPL with Figwheel-main and rebel readline - swap app-state](/images/clojurescript-project-reagent-repl-require-in-ns-swap.png)


As soon as the `swap!` expression is evaluated, the web page for the project is automatically updated.

![ClojureScript REPL with Figwheel-main and rebel readline - swap app-state - web page updated](/images/clojurescript-project-reagent-app-state-updated-in-repl-webpage-result.png)

Add the `swap!` expression as a rich comment block to the `src/practicalli/landing_page.cljs` source code file.

```clojure
(comment
 (swap! app-state assoc :text "Hello from the REPL")
)
```
