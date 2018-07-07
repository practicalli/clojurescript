# Test Figwheel

> ####Note::Test Figwheel via the REPL
> Verify figwheel is working by entering the following code at the REPL prompt in the terminal window.
>
> This will be the same terminal window in which you ran `lein figwheel`
```clojure
(js/alert "Am I connected to the browser repl with figwheel?")
```


[![Test figwheel - a JavaScript alert box from ClojureScript](/images/clojurescript-project-reagent-tictactoe--js-alert-test-code.png)](/images/clojurescript-project-reagent-tictactoe--js-alert-test-code.png)


An alert box should appear in the browser window that opened when figwheel was run.

[![Figwheel quick test: alert box](/images/clojurescript-project-reagent-tictactoe--js-alert-test.png)](/images/clojurescript-project-reagent-tictactoe--js-alert-test.png)


<hr />

> ####Note::Test Figwheel from source code changes
> Verify figwheel is working by editing the code in the file `src/tictactoe-reagent/core.cljs`.
>
> Find the `hello-world` function and change the last line to show a different message
```clojure
(defn hello-world []
  [:div
   [:h1 (:text @app-state)]
   [:h3 "Changes in the code are loaded as soon as you save the file!"]])
```


[![Test figwheel - update ClojureScript code in the editor](/images/)](/images/)
