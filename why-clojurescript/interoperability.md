# Interoperability



Using Javascript functions and libraries is very easy from Clojurescript, its also really easy to make your Clojurescript accessible from Javascript too.



![Clojurescript Interoperability & Transit](/images/clojurescript-interop-code-transit.png)


## Importing Javascript

The CLJ JS website provides a huge range of Javascript libraries that can simply be added as a dependency to your Clojurescript code.  It acts as package management tool for Javascript libraries and makes those packages available via a web-based library.

Since ClojureScript 0.0-2727 the `:foreign-libs` option provides an excellent way to integrate Javascript into ClojureScript applications. CLJSJS provides Javascript libraries and their appropriate extern files packaged up with deps.cljs. CLJSJS aims to concentrate packaging efforts to make everyone’s life a little easier.

![Cljs js packages example](clojurescript-cljs-packages-examples.png)

