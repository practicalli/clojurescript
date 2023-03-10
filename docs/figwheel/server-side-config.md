# Server-side Config


This is not neccessary but you can configure the figwheel system. At
the root level of your `project.clj` you can add the following server
side configuration parameters:

```clojure
:figwheel {
   :http-server-root "public" ;; this will be in resources/
   :server-port 3449          ;; default
   :server-ip   "0.0.0.0"     ;; default

   ;; CSS reloading (optional)
   ;; :css-dirs has no default value 
   ;; if :css-dirs is set figwheel will detect css file changes and
   ;; send them to the browser
   :css-dirs ["resources/public/css"]

   ;; Server Ring Handler (optional)
   ;; if you want to embed a ring handler into the figwheel http-kit
   ;; server
   :ring-handler example.server/handler

   ;; Clojure Macro reloading
   ;; disable clj file reloading
   ; :reload-clj-files false
   ;; or specify which suffixes will cause the reloading
   ; :reload-clj-files {:clj true :cljc false}

   ;; To be able to open files in your editor from the heads up display
   ;; you will need to put a script on your path.
   ;; that script will have to take a file path and a line number
   ;; ie. in  ~/bin/myfile-opener
   ;; #! /bin/sh
   ;; emacsclient -n +$2 $1
   ;;
   :open-file-command "myfile-opener"

   ;; if you want to disable the REPL
   ;; :repl false

   ;; to configure a different figwheel logfile path
   ;; :server-logfile "tmp/logs/figwheel-logfile.log" 

   ;; Start an nREPL server into the running figwheel process
   ;; :nrepl-port 7888

   ;; Load CIDER, refactor-nrepl and piggieback middleware
   ;;  :nrepl-middleware ["cider.nrepl/cider-middleware"
   ;;                     "refactor-nrepl.middleware/wrap-refactor"
   ;;                     "cemerick.piggieback/wrap-cljs-repl"]
} 
```
