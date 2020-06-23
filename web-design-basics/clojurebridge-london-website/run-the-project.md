# Run the project

## On the command line

Change into the directory `clojurebridge-landing-page` and run the command

`lein fig:build`

or

`clojure -A:fig:build`

## Spacemacs

`SPC f f` and open the file `clojurebridge-landing-page/src/clojurebridge_landing_page/core.cljs`

`, "` or `, s I` to run the command `clojurescript-jack-in`

When prompted for the REPL type, select `figwheel-main`

![Spacemacs - ClojureScript REPL - prompt for REPL type](/images/cljs-website-run-spacemacs-repl-type.png)

When prompted for the build, type `dev`

![Spacemacs - ClojureScript REPL - figwheel-main build name](/images/cljs-website-run-spacemacs-build-dev.png)


After a few moments, your default browser will automatically open at [http://localhost:9500/]

![ClojureScript project - initial website](/images/cljs-website-run--webpage.png)
