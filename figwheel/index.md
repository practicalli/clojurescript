# Figwheel

> #### WARNING::Figwheel is superseded by Figwheel-main
> The content refers to the original version of Figwheel which has now been replaced by figwheel-main
>
> New projects should used figwheel-main as figwheel is no longer developed.  This content may be useful for maintaining older projects until they can be migrated to figwheel-main.  The application code should be largely the same between the two tools.


Figwheel builds your ClojureScript code and hot loads it into the browser as you are coding!

* A 6 minute [flappy bird demo of figwheel](https://www.youtube.com/watch?v=KZjFVdU8VLI)
* A more detailed 45 minute [talk on Figwheel](https://www.youtube.com/watch?v=j-kj2qwJa_E) given at ClojureWest 2015.
* An [introductory blog post](http://rigsomelight.com/2014/05/01/interactive-programming-flappy-bird-clojurescript.html).

####Current version:
[![Clojars Project](https://clojars.org/lein-figwheel/latest-version.svg)](https://clojars.org/lein-figwheel)

![Figwheel heads up example](https://s3.amazonaws.com/bhauman-blog-images/figwheel_image.png)


## Live code reloading

If you write [**reloadable code**](https://github.com/bhauman/lein-figwheel#writing-reloadable-code), figwheel can facilitate automated live interactive programming. Every time you save your ClojureScript source file, the changes are sent to the browser so that you can see the effects of modifying your code in real time.

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

## Doesn't load code that is generating warnings

If your ClojureScript code is generating compiler warnings Figwheel won't load it. This, again, is very helpful in keeping the client environment stable. This behavior is optional and can be turned off.


## Supports Node.js

You can [use figwheel to live code ClojureScript in Node.js](https://github.com/bhauman/lein-figwheel/wiki/Node.js-development-with-figwheel)!

## Static file server

The inclusion of a **static file server** allows you to get a decent ClojureScript development environment up and running quickly. For convenience there is a `:ring-handler` option so you can load a Clojure ring handler into the figwheel server.


[appreciation of ClojureScript for design](https://precursorapp.com/blog/clojure-is-a-product-design-tool)
