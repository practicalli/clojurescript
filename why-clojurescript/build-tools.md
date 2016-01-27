# Build Tools

In Clojure & Clojurescript development there is one tool that does all the build automation, this is called Leiningen.

Leiningen uses a declarative approach to defining a project and uses common naming conventions for projects and libraries.  The build configuration is held in a file called `project.clj` that lives in the root of the Clojure / Clojurescript project.

Leiningen is written in Clojure and requires the Java runtime environment (Java JRE) to run.  No Java programming is required to use it.

![Leiningen](/images/leiningen-logo.jpg)

## Leiningen Plugins

There are a great many plugins for Leiningen that extend its functionality.  The most important for Clojurescript is called [Figwheel]().  Figwheel provides a connection between your Clojurescript code and the running JavaScript code in your browser.

We will cover Figwheel in more detail very soon

## Leiningen Templates

There are a number of really good templates to help you configure your projects as you create them.  Rather than just create a project with `lein new my-project-name` you can include a template, `lein new template-name my-project-name` 

Notable templates for Clojurescript include
* figwheel
* chestnut
* [bounce-web](https://clojars.org/bounce-webapp/lein-template)
* [Petrol](https://github.com/krisajenkins/petrol) - A simple event-handling framework

> **Hint** There is a new build automation tool called [boot]() that takes a programatic approach to defining builds and may have some advantage if you want a highly customised build.  At the moment though, this still requires more initial setup to get going than Leiningen.

## Comparing to JavaScript world

In the JavaScript world its not just a case of learning one or two tools, typically you have to learn a number of different tools and learn how to use them well together.

![JavaScript tooling](/images/clojurescript-skeptics-javascript-tooling.png)
