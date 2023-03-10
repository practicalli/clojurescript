![ClojureScript and Figwheel-main banner](https://raw.githubusercontent.com/practicalli/graphic-design/live/banners/clojuresript-figwheel.png)

This is a simple ClojureScript project with no additional application dependencies.  The project uses figwheel-main as a ClojureScript development tool, for live loading of changes into the browser and also for building the projects with different configurations.

{% tabs deps="Clojure CLI project", lein="Leiningen project" %}

{% content "deps" %}
Create a Clojure CLI tools `deps.edn` project using the `:project/new` alias from [practicalli/clojure-deps-edn]({{ book.P9IClojureDepsEdnInstall }})  configuration.

Run this command in a terminal window

```shell
clojure -X:project/new :template figwheel-main :name practicalli/landing-page
```

The command will create a new directory with the project name

![Command line: run ClojureScript REPL with Figwheel-main and rebel readline](/images/clojurescript-project-new-figwheel-main.png)


{% content "lein" %}
Create a Leiningen `project.clj` project using the following command, including `--reagent` which is a common library for reactive web page development

```shell
lein new figwheel-main practicalli/landing-page
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

Also use `:repl/rebel` alias from [practicalli/clojure-deps-edn]({{ book.P9IClojureDepsEdnInstall }}) to run the REPL with rebel readline for a richer REPL experience.


```shell
clojure -M:fig:build
```


{% content "leinrepl" %}

Use Leiningen to run the ClojureScript project using the `:fig` alias and the `:build` build task.

```shell
lein fig:build
```


{% endtabs %}

A window or tab should automatically open once the project starts.  This takes a few moments, so take a few deep breaths.

![ClojureScript REPL with Figwheel-main - default webpage](/images/clojurescript-figwheel-main-default-webpage.png)


## Check the browser connection
Check the browser REPL is connected by evaluating a ClojureScript expression in the ClojureScript REPL.

In the terminal at the ClojureScript REPL prompt, show an alert box in the browser.
```clojure
(js/alert "Hello from the ClojureScript REPL")
```


![Command line: run ClojureScript REPL with Figwheel-main and rebel readline](/images/clojurescript-project-repl-javascript-alert-code.png)

The web page updates and shows a dialog box with the message.

![ClojureScript REPL with Figwheel-main - default webpage](/images/clojurescript-figwheel-main-default-webpage-alert.png)


Add the `js/alert` expression as a rich comment block to the `src/practicalli/landing_page.cljs` source code file.  This provides a convenient way to test the figwheel-main connection to the browser without being part of the main code.

```clojure
(comment
 (js/alert "Hello from the ClojureScript REPL")
)
```
