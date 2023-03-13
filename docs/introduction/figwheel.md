# Figwheel

![figwheel logo name](https://raw.githubusercontent.com/practicalli/graphic-design/live/logos/practicalli-figwheel-logo-name.svg){align=right loading=lazy}


Figwheel builds your ClojureScript code and hot loads it into the browser as you are coding!

* A 6 minute [flappy bird demo of figwheel](https://www.youtube.com/watch?v=KZjFVdU8VLI)
* A more detailed 45 minute [talk on Figwheel](https://www.youtube.com/watch?v=j-kj2qwJa_E) given at ClojureWest 2015.
* An [introductory blog post](http://rigsomelight.com/2014/05/01/interactive-programming-flappy-bird-clojurescript.html).

!!! INFO "Current version"
    ```clojure
    com.bhauman/figwheel-main {:mvn/version "0.2.18"}
    ```

![Figwheel heads up example](https://s3.amazonaws.com/bhauman-blog-images/figwheel_image.png)


??? WARNING "Figwheel-main superseds Figwheel"
    New projects should use `figwheel-main` library as figwheel is no longer developed.  Clojure application code should be largely the same between the two tools, so should be relatively easy to migrate.

    Any content refering to the original version of Figwheel should be replaced by figwheel-main


## Live code reloading

Write [**reloadable code**](https://github.com/bhauman/lein-figwheel#writing-reloadable-code) to ensure figwheel can facilitate automated live interactive programming. Every time a ClojureScript source file is saved the changes are sent to the browser to show the effects of modifying your code in real time.

This live code reloading also applies to CSS & JavaScript.


## Heads up display

Figwheel has a non-intrusive heads up display that gives you feedback on how well your project is compiling. By writing a shell script you can click on files in the heads up display and they will open in your editor!


## Built-in ClojureScript REPL

When you launch figwheel it not only starts a live building/reloading process but it also optionally launches a CLJS REPL into your running application. This REPL shares compilation information with the figwheel builder, so as you change your code the REPL is also aware of the code changes. The REPL also has some special built-in control functions that allow you to control the auto-building process and execute various build tasks without having to stop and rerun lein-figwheel.


## Robust connection

Figwheel's connection is fairly robust with sessions that can last for days through multiple OS sleeps. You can also use figwheel like a REPL if you are OK with using `print` to output the evaluation results to the browser console.


## Message broadcast

Figwheel **broadcasts** changes to all connected clients. This means you can see code and CSS changes take place in real time on your phone and in your laptop browser simultaneously.


## Respects dependencies

Figwheel will not load a file that has not been required. It will also respond well to new requirements and dependency tree changes.


## Calculates minimal reload set

Figwheel does its best to only reload what needs to be reloaded. This minimizes the surface area of dynamically reloaded code, which in turn should increase the stability of the client environment.

ClojureScript code that generates compiler warnings is not loaded into the browser by Figwheel, keeping the client environment stable. This behaviour is optional and can be turned off.


## Node.js Support

You can [use figwheel to live code ClojureScript in Node.js](https://github.com/bhauman/lein-figwheel/wiki/Node.js-development-with-figwheel)!


## Static file server

Figwheel includes a **static file server**

`:ring-handler` option allows loading of a Clojure ring handler into the figwheel server.


[appreciation of ClojureScript for design](https://precursorapp.com/blog/clojure-is-a-product-design-tool)
