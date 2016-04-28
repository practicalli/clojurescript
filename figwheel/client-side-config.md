# Client-side Config


Make sure you have setup an html file to host your cljs. For example
you can create this `resources/public/index.html` file:

```html
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
    <div id="main-area">
    </div>
    <script src="js/example.js" type="text/javascript"></script>   
  </body>
</html>
```

## Client side configuration options 

Instead of setting `:figwheel true` in your cljsbuild configuration
you can pass a map of options as below:

```clojure
:cljsbuild {
  :builds [ { :id "example" 
              :source-paths ["src/"]

              ;; put client config options in :figwheel
              :figwheel { :websocket-host "localhost" 
                          :on-jsload "example.core/fig-reload"}
                          
              :compiler {  :main "example.core"
                           :asset-path "js/out"
                           :output-to "resources/public/js/example.js"
                           :output-dir "resources/public/js/out"
                           :optimizations :none } } ]
}
```

The following configuration options are available:

```clojure

;; configure a websocket host, figwheel already knows the port
;; this is helpful if you want to broadcast to devices
:websocket-host "localhost" ;; or "www.myhost.com", "192.168.0.112"

;; An important configuration option for :websocket-host
;; if you set it to :js-client-host it will set the host based on the
;; js/location.host param of the browser
;; This is helpful for multiple device settings where you are using
;; fighweel to serve your app.
;; :websocket-host :js-client-host

;; optional callback
:on-jsload "example.core/fig-reload"

;; if you want to do REPL based development and not have
;; have compiled files autoloaded into the client env
:autoload false

;; The heads up display is enabled by default to disable it: 
:heads-up-display false

;; when the compiler emits warnings figwheel blocks the loading of files.
;; To disable this behavior:
:load-warninged-code true
```

Whole files will be reloaded on change so we have to make sure that
we [write reloadable code](https://github.com/bhauman/lein-figwheel#writing-reloadable-code).

Please check out the example project in the `example` directory.

To see all the client side config options [look here](https://github.com/bhauman/lein-figwheel/blob/master/support/src/figwheel/client.cljs#L254).

