# Figwheel-main Workflow

![figwheel logo name](https://raw.githubusercontent.com/practicalli/graphic-design/live/logos/practicalli-figwheel-logo-name.svg){align=right loading=lazy}

[Figwheel-main](https://figwheel.org/) build tool and [Rebel rich terminal UI](https://practical.li/clojure/clojure-cli/repl/) is a simple way to get started with ClojureScript development

The [figwheel-main template](https://github.com/bhauman/figwheel-main-template) creates a project with Clojure CLI configuration, providing example code and build configurations for development, testing and deployment workflows which are explored in some detail.


## Overview

Using Figwheel provides an simple way to develop, test and deploy ClojureScript projects, providing instant feedback as you develop to see exactly what the code does and help minimise bugs and avoid inappropriate design choices.

Add aliases and build configurations customise the workflows for greater flexibility.  The configuration files are EDN, so are Clojure maps that are simple to work with and understand.

There are more examples of options for figwheel-main projects on the https://figwheel.org/ website.

> lambdaisland/kaocha-cljs enables using kaocha test runner with ClojureScript project, although I am still working on an example once I've resolved [an issue with the configuration](https://github.com/lambdaisland/kaocha-cljs/issues/48)


![Figwheel-main example screenshot of development](https://s3.amazonaws.com/bhauman-blog-images/figwheel-main/figwheel-main-demo-image.png)



??? INFO "Current version"
    ```clojure
    com.bhauman/figwheel-main {:mvn/version "0.2.18"}
    ```
