# Scripting Figwheel


As your development workflow grows in complexity, the declarative
approach of `lein` can be limiting when you want to launch and control
different services (ie. SASS compilation). It is really helpful to use
Clojure itself to script whatever workflow services you want.

Figwheel has a Clojure
[API](https://github.com/bhauman/lein-figwheel/blob/master/sidecar/src/figwheel_sidecar/repl_api.clj)
that makes it easy to start, stop and control Figwheel from Clojure.

In order for the following examples to work, you will need to have
`[figwheel-sidecar "0.5.0-2"]` in your dependencies.

To start Figwheel from a script, you will need to require the
`figwheel-sidecar.repl-api` and provide your build configuration to
`figwheel-sidecar.repl-api/start-figwheel!` like so:

```clojure
(require '[figwheel-sidecar.repl-api :as ra])

;; this will start figwheel and will start autocompiling the builds specified in `:builds-ids`
(ra/start-figwheel!
  {:figwheel-options {} ;; <-- figwheel server config goes here 
   :build-ids ["dev"]   ;; <-- a vector of build ids to start autobuilding
   :all-builds          ;; <-- supply your build configs here
   [{:id "dev"
     :figwheel true
     :source-paths ["src"]
     :compiler {:main "example.core"
                :asset-path "out"
                :output-to "resources/public/main.js"
                :output-dir "resources/public/out"
                :verbose true}}]})
                
;; you can also just call (ra/start-figwheel!)
;; and figwheel will do its best to get your config from the
;; project.clj or a figwheel.edn file

;; start a ClojureScript REPL
(ra/cljs-repl)
;; you can optionally supply a build id
;; (ra/cljs-repl "dev")
```

>  **Build config notes**
>
>  It's important to remember that figwheel can autobuild and reload
>  multiple builds at the same time. It can also switch between builds
>  and focus on autobuilding one at a time. For this reason you need
>  to supply the initial `:build-ids` to tell figwheel which builds
>  you want to start building. It's also really helpful to supply your
>  `:advanced` builds because while you can't autobuild them you can
>  call `build-once` on them

Assuming the above script is in `script/figwheel.clj` you can invoke it as follows:

```
$ rlwrap lein run -m clojure.main script/figwheel.clj
```

The above command will start figwheel and it will behave just like
running `lein figwheel`.

Please note that the above command is not running the script in the
same environment as `lein repl` or `cider-jack-in`. Both of these
start an nREPL session. I am intentionally not using nREPL in order to
remove a lot of complexity from ClojureScript REPL communication.

> If you are using nREPL, launching the ClojureScript REPL
> requires that you have Piggieback installed. Please see the section
> above titled "Editor REPLs and nREPL"

Let's make a small helper library and then initialize a Clojure REPL with it:

```clojure
(require
 '[figwheel-sidecar.repl-api :as ra])

(defn start []
  (ra/start-figwheel!
    {:figwheel-options {} ;; <-- figwheel server config goes here 
     :build-ids ["dev"]   ;; <-- a vector of build ids to start autobuilding
     :all-builds          ;; <-- supply your build configs here
     [{:id "dev"
       :figwheel true
       :source-paths ["src"]
       :compiler {:main "example.core"
                  :asset-path "out"
                  :output-to "resources/public/main.js"
                  :output-dir "resources/public/out"
                  :verbose true}}]}))

;; Please note that when you stop the Figwheel Server http-kit throws
;; a java.util.concurrent.RejectedExecutionException, this is expected

(defn stop []
  (ra/stop-figwheel!))

(defn repl []
  (ra/cljs-repl))
```

The next line will call `clojure.main` and initialize it with our
script and then continue on to launch a REPL.

```
$ rlwrap lein run -m clojure.main --init script/figwheel.clj  -r
```

After the Clojure REPL has launched, you will now have the ability to
call `(start)`, `(repl)` and `(stop)` as you need.

You can also call all of the functions in the [figwheel-sidecar.repl-api](https://github.com/bhauman/lein-figwheel/blob/master/sidecar/src/figwheel_sidecar/repl_api.clj).

This is a powerful way to work, as you now have the interactivity and
generality of the Clojure programming language available.

Need to start a server? Go for it.<br/>Need to watch and compile SASS files? No problem.
