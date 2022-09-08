# Packaging the project

Building ClojureScript applications with Figwheel generates lots of files under `target/public`, as this is the most efficient way to push changes to the JavaScript engine application during development.  Using only a single file when deploying your application to the live system makes your application website faster to load (only one http request).

> The ClojureScript compiler has four :optimizations modes :none, :whitespace, :simple and :advanced.

The `figwheel-main` template provides a `:min` alias to generate a single minified file that has been run through the Google Closure compiler to eliminate any uncalled code.  This generates a single file called `target/public/cljs-out/dev-main.js`

Publish the application by manually copying the file to a suitable deployment directory (or write a script to do so) when you publish your application live.
