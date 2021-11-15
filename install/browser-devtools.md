# Browser developer tools

Developer tools included in browsers (FireFox, Google Chrome, etc.) allow examination of what is happening when you run the JavaScript code created from your ClojureScript code.

* [Firefox Developer Tools](https://developer.mozilla.org/en-US/docs/Tools)
* [Google Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/)

| Feature                                                                                           | Description                                                              |
|---------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| [Page Inspector](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector)                   | view / edit the source code of the page                                  |
| [Web Console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console)                         | see log messages and interact with current page via code                 |
| [JavaScript debugger](https://developer.mozilla.org/en-US/docs/Tools/Debugger)                    | stop, step through, examine, and modify the JavaScript running on a page |
| [Source Maps](#source-maps)                                                                       | format the original ClojureScript code in the browser                    |
| [Network monitor](https://developer.mozilla.org/en-US/docs/Tools/Network_Monitor)                 | Network requests when a page is loaded                                   |
| [Performance Tools](https://developer.mozilla.org/en-US/docs/Tools/Performance)                   | Analyze a pages responsiveness, JavaScript and layout performance        |
| [Application panel](https://developer.mozilla.org/en-US/docs/Tools/Application)                   | Inspect and debug progressive apps, service workers and app manifests    |
| [Responsive design mode](https://developer.mozilla.org/en-US/docs/Tools/Responsive_Design_Mode)   | UI look and behavior of page on different devices and network types      |
| [Accessibility Inspector](https://developer.mozilla.org/en-US/docs/Tools/Accessibility_inspector) | Report on accessibility support of a page                                |


## Supporting tools
* [cljs-dev-tools](https://github.com/binaryage/cljs-devtools)


## Learning Resources

* [What are browser developer tools](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools)
* [15 must know Chrome DevTools tips](http://tutorialzine.com/2015/03/15-must-know-chrome-devtools-tips-tricks/) by Tutorialzine.com


## Source Maps

[Source Maps](https://clojurescript.org/reference/source-maps) show you what ClojureScript code created the running JavaScript to aid with debugging.

Ensure source maps are enabled in the browser developer tools.

![Chrome DevTools - inline source maps](/images/chrome-devtools-inline-source-maps.png)


# Chrome DevTools Extensions for ClojureScript developers

DevTool Extensions add more better presentation of ClojureScript values in Chrome DevTools using custom formatters, more informative exceptions with sanity hints) and support for [Dirac DevTools](https://github.com/binaryage/dirac) - a fork of the Chrome DevTools.


![Chrome DevTools Extensions - ClojureScript data structure formatting](/images/chrome-devtools-clojurescript-data-structure-formatting.png)


## Install DevTools Extensions

Add devtools dependency into your Leiningen's project.clj using the details on the [Clojars.org](https://clojars.org/binaryage/devtools) website

Add the DevTools extensions to the startup part of your ClojureScript using the `(:require [devtools.core :as devtools])` expression.  Then call `install!` function from `devtools.core` namespace.

Here is an example of adding the DevTools extension library and calling it with several options

```clojure
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


## References

* [Write a Firefox add-on in ClojureScript](https://bhoot.sh/how-to-write-a-firefox-addon-in-clojurescript.html)
