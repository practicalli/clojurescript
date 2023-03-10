# Check figwheel configuration

Ensure figwheel is configured correctly by calling `figwheel.main` without a build configuration.  The ClojureScript code for the project is not compiled so cannot be the cause of any failure or warnings.

This is quick way to identify if issues are from figwheel configuration or from ClojureScript code.

```shell
clojure -M:fig -m figwheel.main
```

A web browser window will open showing the figwheel website, contains the fundamental documentation for developing with Figwheel.

![Figwheel-main - REPL host page](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojurescript/figwheel/figwheel-main-repl-host-page.png)
