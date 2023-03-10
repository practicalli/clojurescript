# Running figwheel and building the project

Calling figwheel with a build configuration compiles the project ClojureScript code into JavaScript as figwheel starts.  The JavaScript code is sent to the JavaScript engine in the browser window that figwheel opened.

Saved changes to the project ClojureScript files will automatically generate updates to the JavaScript code and send them to the JavaScript engine in the browser.

The `:build` alias is used during development of a ClojureScript project

```shell
clojure -M:fig:build
```

![Figwheel-main - project - hello world](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojurescript/figwheel/figwheel-main-project-hello-world-page.png)


> The `:build` alias defines `figwheel.main` as the main namespace and the arguments passed to the `-main` function in that namespace.
> `"-b" "dev"` will used `dev.cljs.edn` as the configuration, `-r` option to run a REPL prompt (in this case using Rebel)
>
> `:build {:main-opts ["-m" "figwheel.main" "-b" "dev" "-r"]}`
>
> This configuration is the equivalent of running the command `clojure -M:fig -m figwheel.main -b dev -r`
