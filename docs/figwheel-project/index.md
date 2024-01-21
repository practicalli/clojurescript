# Figwheel Project

In this section we will create a ClojureScript project using Figwheel to manage the build and auto-reloading of changes into the project

  * [Create Project](create-project.md)
  * [ClojureScript file](clojurescript-file.md)
  * [Project Build file](project-build-file.md)
  * [Run Figwheel](run-figwheel.md)
  * [Web Page](web-page.md)
  * [Run Figwheel again](run-figwheel-again.md)
  * [Add a counter](add-a-counter.md)
  * [Auto Reloading](auto-reloading.md)
  * [Serving assets](serving-assets.md)
  * [Using the REPL](using-the-repl.md)


> Understanding how Figwheel works provides clarity should a change to the project build file be required


The figwheel-main template will create the configuration files and directory structure for a project, including a simple working app.  

=== "Practicalli Clojure CLI Config"
    `:project/create` alias is provided by [Practicalli Clojure CLI Config](https://practical.li/clojure/clojure-cli/practicalli-config/) and uses the [deps-new]() tool to create projects, optionally with [Practicalli Project Templates](https://practical.li/clojure/clojure-cli/projects/templates/practicalli/)

    Create a new project using the [`practicalli/landing-page` template](https://practical.li/clojure/clojure-cli/projects/templates/practicalli/landing-page/){target=_blank}.

    ```shell
    clojure -T:project/create :template practicalli/landing-page :name practicalli/website-name
    ```

    `src/practicalli/landing_page.clj` is the main ClojureScript source code file which is used to generate the JavaScript app loaded into the browser.

