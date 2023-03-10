# Editor support with ClojureScript Figwheel-main projects
Using an editor provides the full REPL driven development experience,

Clojure aware editors can connect to an existing REPL or start a REPL for a ClojureScript project and then connect, referred to as jack-in.


## Jack-in
The editor will inject the required libraries as dependencies, start the REPL and connect the editor to the REPL process

Open the ClojureScript project in the editor, a `.cljs` or `.edn` file.

{% tabs spacemacs="spacemacs", calva="VSCode Calva" %}

{% content "spacemacs" %}

`, '` to run the `sesman-start` command

Select `cider-jack-in-cljs`

Select `figwheel-main`

Select the `dev` build

{% content "lein" %}
`, '` to run the `sesman-start` command

Select `cider-jack-in-cljs`

Select `Leiningen`

Select the `dev` build



{% endtabs %}


## Connect
Run the project from the command line, adding in an alias that includes the libraries needed to run

[`practicalli/clojure-deps-edn`]({{book.P9IClojureDepsEdn}})

```shell
clojure -M:figwheel:build:middleware/cider-cljs
```

> Not sure if the :build alias is required

Open the ClojureScript project in the editor

Run the **connect** command (Cider: `cider-connect-cljs`, Calva: )

Select `figwheel-main`

Select `dev` build



> Conjure should connect automatically when it detects a `.nrepl-port` file in the root of the project



I've been tidying up the Practicalli ClojureScript book and deprecating much of the content (which might still work but needs reviewing).  The focus of the book over the next few months will be building websites with reagent (maybe some simple reframe) using figwheel-main.
