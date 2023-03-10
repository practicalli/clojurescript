# Run webserver

> **Note** Run the webserver we use Leiningen, the Clojure build automation tool.  In the root of your Clojure project, the directory that contains `project.clj`

In a command line terminal, navigate to the root of your project and type the following command

```bash
lein run 8000
```

  This command should start up a Jetty web server that listens on http://localhost:8000.

![](../images/todo-list-lein-run-portnumber.png)

> **Note** Open http://localhost:8000 in your browser and try out different pages, such at [/hello]( http://localhost:8000/hello),  [/goodbye]( http://localhost:8000/goodbye) or  [/complete-indifference]( http://localhost:8000/complete-indifference).  It should not matter what page you visit, you should get the same response.

![todo-list project in the browser](../images/todo-list-lein-run-browser.png)

---

## The project so far 

  The code and configuration we have created so far are in the [clojure-webapps-example](https://github.com/practicalli/clojure-webapps-example) github repository, specifically the branch called `01-create-a-webserver`
  
  If something is not working or you want to speed up, simply clone the project into a new directory using the command:

```bash
git clone https://github.com/practicalli/clojure-webapps-example 
```
Once you have cloned the project, checkout the `01-create-a-webserver` branch

```
git checkout 01-create-a-webserver
```
