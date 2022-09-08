# Running tests once

The `test` directory contains source code for unit tests, using a directory path matching the namespace they are testing from the `src` directory.  `-test` is added to the end of the test namespaces.  For example, if we have a source namespace of `practicalli.hello-world`, the tests would be in `practicalli.hello-world-test`.

![ClojureScript - figwheel-main src and test trees](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojurescript/figwheel/figwheel-project-src-and-test-trees.png)

Use the `:test` alias with the `:fig` alias to run the Figwheel test runner

```shell
clojure -M:fig:test
```

This will open a browser and connect to its JavaScript REPL and run the tests.

![Figwheel-main test runner - test host page](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojurescript/figwheel/figwheel-main-test-runner-test-host-page.png)

The results of the test run are printed to the terminal

![Figwheel-main - test output in terminal](/images/figwheel-main-test-output-terminal.png)

> Running tests this way may not be as fast as using the continuous testing approach (covered next)


## Test configuration

The `:test` alias uses the `test.cljs.edn` build configuration to start the Figwheel test runner and runs all the test namespaces under the `test` directory.

`:test  {:main-opts ["-m" "figwheel.main" "-co" "test.cljs.edn" "-m" practicalli.test-runner]}`

The `test.cljs.edn` build configuration defines a separate URL to open the test host page, to avoid clashing with the URL to connect to the ClojureScript application itself.

```clojure
^{
  ;; alternative landing page for the tests to avoid launching the application
  :open-url "http://[[server-hostname]]:[[server-port]]/test.html"

  ;; launch tests in a headless environment - update path to chrome on operating system
  ;; :launch-js ["/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" "--headless" "--disable-gpu" "--repl" :open-url]
  }
{:main practicalli.test-runner}
```
