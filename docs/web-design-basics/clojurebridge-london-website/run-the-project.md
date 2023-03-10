# Run the project

On the command line, change into the directory `landing-page` and run the command to start building the project

{% tabs deps="Clojure CLI", lein="Leiningnen", spacemacs="Spacemacs"  %}

{% content "deps" %}

```bash
clojure -M:fig:build
```

{% content "lein" %}

```bash
lein fig:build
```

{% content "spacemacs" %}

## Spacemacs and Cider Jack-in

`SPC f f` to open the file `landing-page/src/clojurebridge/landing_page.cljs`

`, m s` (`sesman-start`) and select the command `cider-jack-in-cljs`

When prompted for the REPL type, select `figwheel-main`

![Spacemacs - ClojureScript REPL - prompt for REPL type](/images/cljs-website-run-spacemacs-repl-type.png)

When prompted for the build, type `dev`

![Spacemacs - ClojureScript REPL - figwheel-main build name](/images/cljs-website-run-spacemacs-build-dev.png)

{% endtabs %}



After a few moments, the default web browser will automatically open at [http://localhost:9500/] and show the running ClojureScript application.

![ClojureScript project - initial website](/images/cljs-website-run--webpage.png)
