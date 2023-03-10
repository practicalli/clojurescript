# Scripting with Component


I highly recommend Stuart Sierra's
[component](https://github.com/stuartsierra/component) library to
compose all the services you will need in your development process.

Here is an example of creating a Figwheel component and composing it
with a Ring server component to serve your application.

```clojure
(require
 '[figwheel-sidecar.repl-api :as ra]
 '[com.stuartsierra.component :as component]
 '[ring.component.jetty :refer [jetty-server]])

(def figwheel-config
   {:figwheel-options {} ;; <-- figwheel server config goes here 
    :build-ids ["dev"]   ;; <-- a vector of build ids to start autobuilding
    :all-builds          ;; <-- supply your build configs here
    [{:id "dev"
      :figwheel true
      :source-paths ["src/main"]
      :compiler {:main "example.core"
                 :asset-path "/out"
                 :output-to "resources/public/main.js"
                 :output-dir "resources/public/out"
                 :verbose true}}]})

(defrecord Figwheel []
  component/Lifecycle
  (start [config]
    (ra/start-figwheel! config)
    config)
  (stop [config]
    ;; you may want to restart other components but not Figwheel
    ;; consider commenting out this next line if that is the case
    (ra/stop-figwheel!)
    config))

(defn handler [request]
  {:status  200
   :headers {"Content-Type" "text/plain"}
   :body    "Hello World"})

(def system
  (atom
   (component/system-map
    :app-server (jetty-server {:app {:handler handler}, :port 3000})
    :figwheel   (map->Figwheel figwheel-config))))

(defn start []
  (swap! system component/start))

(defn stop []
  (swap! system component/stop))

(defn reload []
  (stop)
  (start))

(defn repl []
  (ra/cljs-repl))
```

Again you can run this script as so:

```
$ rlwrap lein run -m clojure.main --init script/figwheel.clj  -r
```

As you can see with humble beginnings you can build up arbitrary
functionality.

Please see Daniel Szmulewicz's excellent [system](https://github.com/danielsz/system) which is
a set of helpful [components](https://github.com/danielsz/system)

> If you are using nREPL, launching the ClojureScript REPL requires
> that you have Piggieback installed. Please see the section above
> titled "Editor REPLs and nREPL"

> Please note that when you stop the Figwheel server, http-kit throws
> a `java.util.concurrent.RejectedExecutionException`, this is expected

Read more about the [`clojure.main`](http://clojure.org/repl_and_main) command line options

Read more about [component](https://github.com/stuartsierra/component)
