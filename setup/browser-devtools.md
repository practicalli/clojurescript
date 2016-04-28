# Browser DevTools

The Google [Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/) help you understand what is happening when you run the JavaScript code created from your ClojureScript code.

  * Online Course: [CodeSchool - Discover DevTools](https://www.codeschool.com/courses/discover-devtools) - sponsored by Google
  * [15 must know Chrome DevTools tips](http://tutorialzine.com/2015/03/15-must-know-chrome-devtools-tips-tricks/) by Tutorialzine.com

## Source Maps

Source Maps show you what ClojureScript code created the running JavaScript.  This can be used for debugging, showing you the breakpoints set in your ClojureScript code

![Chrome DevTools - inline source maps](/images/chrome-devtools-inline-source-maps.png)


# Chrome DevTools Extensions for ClojureScript developers

DevTool Extensions add more better presentation of ClojureScript values in Chrome DevTools using custom formatters, more informative exceptions with sanity hints) and support for [Dirac DevTools](https://github.com/binaryage/dirac) - a fork of the Chrome DevTools.


![Chrome DevTools Extensions - ClojureScript data structure formatting](/images/chrome-devtools-clojurescript-data-structure-formatting.png)


## Install DevTools Extensions

Add devtools dependency into your Leiningen's project.clj using the details on the [Clojars.org](https://clojars.org/binaryage/devtools) website

Add the DevTools extensions to the startup part of your ClojureScript using the `(:require [devtools.core :as devtools])` expression.  Then call `install!` function from `devtools.core` namespace. 

Here is an example of adding the DevTools extension library and calling it with several options

```cljs
(ns your-project.core
  (:require [devtools.core :as devtools]))

; this enables additional features, :custom-formatters is enabled by default
(devtools/enable-feature! :sanity-hints :dirac)
(devtools/install!)

(.log js/console (range 200))
```

For more details, visit the [DevTools Extensions website](https://github.com/binaryage/cljs-devtools) and clone the [sample project](https://github.com/binaryage/cljs-devtools-sample).


## Dirac DevTools (a fork of Chrome DevTools)

[Dirac DevTools](https://github.com/binaryage/dirac) is a fork of the Chrome DevTools.

![Dirac DevTools - a fork of Chrome DevTools](/images/chrome-devtools-dirac-fork.png)
