# Clojurescript projects
A ClojureScript project should contain dependencies for the Clojure and ClojureScript libraries, which are managed by the build tool (Clojure CLI tools or Leiningen) just like any other dependency.

figwheel-main provides additional tooling for REPL driven development, including live updates to the browser REPL and test runner.

Use the `figwheel-main` template to generate a working ClojureScript project with Figwheel-main.

{% tabs deps="Clojure CLI project", lein="Leiningen project" %}

{% content "deps" %}
Create a Clojure CLI tools `deps.edn` project using the `:project/new` alias from [practicalli/clojure-deps-edn]({{ book.P9IClojureDepsEdnInstall }})  configuration, including the `--reagent` template option which adds a common library for reactive web page development

Run this command in a terminal window

```shell
clojure -X:project/new :template figwheel-main :name practicalli/landing-page -- --reagent
```

The command will create a new directory with the project name

![Command line: run ClojureScript REPL with Figwheel-main and rebel readline](/images/clojurescript-project-new-figwheel-main.png)


{% content "lein" %}
Create a Leiningen `project.clj` project using the following command, including `--reagent` which is a common library for reactive web page development

```shell
lein new figwheel-main hello-world.core -- --reagent
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

![ClojureScript REPL with Figwheel-main - default webpage](/images/clojurescript-figwheel-main-default-webpage-alert.png)



> ####Hint::Ensure project runs locally before running from an editor
> Running a ClojureScript project on the command line is a quick way to ensure everything is working before considering running the project via an editor.




## Reference

* [Interactive programming Flappy Birds in ClojureScript](https://www.youtube.com/watch?v=KZjFVdU8VLI)
* [Clojure West 2015 - Developing ClojureScript with Figwheel](https://www.youtube.com/watch?v=j-kj2qwJa_E)


> **Hint** ClojureScript uses the Google Closure compiler and build tools that require a Java Virtual machine.  However, work is in progress to make ClojureScript self hosting.  See articles such as [ClojureScript Next](http://swannodette.github.io/2015/07/29/clojurescript-17/) and [Bootstrapped ClojureScript FAQ](https://github.com/clojure/clojurescript/wiki/Bootstrapped-ClojureScript-FAQ) for pro's and con's of this approach.
