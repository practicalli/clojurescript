# Configure Build


You also need to have your `:cljsbuild` configuration set up in your `project.clj`.

Here is an example:

```clojure
:cljsbuild {
  :builds [ { :id "example" 
              :source-paths ["src/"]
              :figwheel true
              :compiler {  :main "example.core"
                           :asset-path "js/out"
                           :output-to "resources/public/js/example.js"
                           :output-dir "resources/public/js/out" } } ]
}
```

The important part here is that you have to have at least one `build` that has `:optimizations` set to `:none` or `nil`.

If you leave out the `:optimizations` key the ClojureScript compiler will default to `:none`.

Setting `:figwheel true` or `:figwheel { :on-jsload "example.core/reload-hook" }` will automagically insert the figwheel client code into your application.  If you supply `:on-jsload` the name of a function, that function will be called after new code gets reloaded.

> **Hint** If you want to serve the HTML file that will host your application from figwheel's built in server, then the output directory has to be in a directory that can be served by the static webserver. The default for the webserver root is "resources/public" so your output files need to be in a subdirectory "resources/public" unless you change the webserver root. For now the webserver root has to be in a subdirectory of `resources`.

If you are serving your application HTML from your own server you can configure `:output-to` and `:output-dir` as you like.

Start the figwheel server. (This will get the first `:optimizations` `:none` build)

    $ lein figwheel

or optionally give the name of the build

    $ lein figwheel example

This will start a server at `http://localhost:3449` with your resources being served via the compojure `resources` ring handler.

So you can load the HTML file thats hosting your ClojureScript app by going to `http://localhost:3449/<yourfilename>.html`

If you are using your own server please load your app from that server.
