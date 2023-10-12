# Rich REPL UI with Rebel

Figwheel will run Rebel readline to start the REPL, as the `:fig` alias includes `com.bhauman/rebel-readline-cljs` as an extra dependency.

Rebel provides syntax highlighted code, auto-completion, commands to manage the REPL and Clojure documentation help, all within its rich command line.


![Clojure CLI tools - Figwheel-main - rebel readline](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojurescript/figwheel/clojure-cli-figwheel-main-without-build.png)


Typing `:repl/help` as a command at the Rebel prompt shows characters are syntax highlighted. The command provides a quick reference for Rebels capabilities.

![Figwheel-main - repl help](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojure/rebel/rebel-repl-help-menu.png)


Evaluate expressions by typing them at the Rebel prompt and pressing `RET`, e.g. `(map inc [2 4 6 8])`

JavaScript interop code also works from the Rebel prompt, e.g. `(js/alert "Notification from the command line")` will display an alert in the browser.

> Practicalli Clojure provides examples of [using Rebel as a rich terminal UI for the Clojure REPL](https://practical.li/clojure/clojure-cli/repl/)
>
> The `clojure` command should be used to run Rebel.  The `clj` wrapper script calls `rlwrap` which conflicts with Rebel, as they are both readline tools.
