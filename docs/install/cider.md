# CIDER

You can use CIDER, the Emacs client for Clojure, with Clojurescript projects.

In the current version of CIDER you can have both a Clojure and ClojureScript REPL active at the same time, so forms evaluated from a CLJ or CLJS file automatically go to the right place.

Run the command `cider-jack-in-clojurescript` to start two nREPL sessions.

> For a more detailed background to how this works, see the LambdaIsland article ["Using Figwheel With Emacs, part 2: CIDER"](https://lambdaisland.com/episodes/figwheel-emacs-cider) (account required for access)

## Clojurescript environments

You can choose from one of several REPL's to use with CIDER.  By default CIDER is configured to use the Java Rhino REPL, however most people will use Figwheel instead.

CIDER use Rhino, the JavaScript engine bundled with Java. Rhino is useful if you want to use Java classes straight from ClojureScript.

Figwheel is the most common approach for Clojurescript websites.


## Setting the environment

CIDER can be configured by customizing the `cider-cljs-lein-repl` variable. 

This variable is set to `(cemerick.piggieback/cljs-repl (cljs.repl.rhino/repl-env))`so we need to change it for other environments. CIDER makes this easy by providing a list to choose from.

Lets change the setting to use Figwheel:

1. Open the customize interface with `M-x customize-variable cider-cljs-lein-repl`. 

2. Tab your way to the button that reads “Value Menu” and press Enter. 

3. A buffer is displayed with a list of choices, the second of which is “Figwheel sidecar”.  Press 1, and then press the "Apply and Save" button.

Now if you look at `cider-cljs-lein-repl` you’ll see it’s switched to a Figwheel REPL. 

Use Directory Local Variables to change this on a per project basis.

```clojure
(do
  (require 'figwheel-sidecar.repl-api)
  (figwheel-sidecar.repl-api/start-figwheel!)
  (figwheel-sidecar.repl-api/cljs-repl))
```

A more elaborate snippet that tries to detect the type of project and run the appropriate environment.

```clojure
(setq cider-cljs-lein-repl
      "(cond
  (and (resolve 'user/run) (resolve 'user/browser-repl)) ;; Chestnut projects
  (eval '(do (user/run)
             (user/browser-repl)))

  (try
    (require 'figwheel-sidecar.repl-api)
    (resolve 'figwheel-sidecar.repl-api/start-figwheel!)
    (catch Throwable _))
  (eval '(do (figwheel-sidecar.repl-api/start-figwheel!)
             (figwheel-sidecar.repl-api/cljs-repl)))

  (try
    (require 'cemerick.piggieback)
    (resolve 'cemerick.piggieback/cljs-repl)
    (catch Throwable _))
  (eval '(cemerick.piggieback/cljs-repl (cljs.repl.rhino/repl-env)))

  :else
  (throw (ex-info \"Failed to initialize CLJS repl. Add com.cemerick/piggieback and optionally figwheel-sidecar to your project.\" {})))")
```
