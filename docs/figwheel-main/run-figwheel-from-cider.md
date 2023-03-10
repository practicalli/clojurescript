# Run Figwheel-main from Emacs Cider

Figwheel-main projects can be run from Emacs with CIDER using the `cider-jack-in-cljs` command.  The user is prompted for the build name to use.

[Emacs CIDER Jack-in with Clojure CLI projects](https://practicalli.github.io/blog/posts/cider-jack-in-to-clojure-cli-projects-from-spacemacs/) benefits from a `.dir-locals.el` file to set the `:fig` alias (and any other aliases) and the figwheel build configuration when starting the Clojure REPL.

```elisp
((clojure-mode . ((cider-preferred-build-tool          . clojure-cli)
                  (cider-clojure-cli-aliases           . ":fig")
                  (cider-default-cljs-repl             . figwheel-main)
                  (cider-figwheel-main-default-options . "dev")
                  (cider-repl-display-help-banner      . nil))))
```

> Use `cider-connect-cljs` to connect Emacs to a REPL (nREPL) process that is already running, i.e. via the `clojure -M:fig:build` command in the terminal.
