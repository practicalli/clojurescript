# Start the REPL

A REPL will run the project code every time we save files or evaluate expressions.  This provides an instant feedback loop to ensure our application does what we think it should do.

> #### Note::Run the browser-repl using one of the following methods.

> When you see the line `Successfully compiled "resources/public/app.js"` browse to http://localhost:3449 to see the running app.

_It may take 10-30 seconds to start the repl, especially if libraries are to be downloaded.  If nothing is displayed in your browser window, give it a few seconds and refresh the browser._

> #### Hint::
> If you changed the `:figwheel :server-port` number in `project.clj` then you should use that number instead of 3449.


## Using Spacemacs or Emacs & CIDER

Use the command `clojurescript-jack-in` and open a browser at http://localhost:3449 

> #### Hint::Configure Emacs to use browser-repl
>  Add the following elisp code to your `.spacemacs` (in `dotspacemacs/user-config`) or Emacs `.init.el` file to ensure the project (figwheel) runs the **browser-repl** rather than the default **nashorn** repl in the JVM.

``` emacs-lisp
(setq cider-cljs-lein-repl
      "(do (user/run)
           (user/browser-repl))")
```

## Command Line & other editors

Open a terminal and type `lein repl` to start a Clojure REPL or start a REPL from your editor.

In the REPL, enter the following function calls then open a browser at http://localhost:3449 

```clojure
(run)

(browser-repl)
```

The call to `(run)` starts the Figwheel server at port 3449, which takes care of
live reloading ClojureScript code and CSS. Figwheel's server will also act as
your app server, so requests are correctly forwarded to the http-handler you
define.

Running `(browser-repl)` starts the Figwheel ClojureScript REPL. Evaluating
expressions here will only work once you've loaded the page, so the browser can
connect to Figwheel.

When you see the line `Successfully compiled "resources/public/app.js" in 21.36
seconds.`, you're ready to go. Browse to `http://localhost:3449` and enjoy.

