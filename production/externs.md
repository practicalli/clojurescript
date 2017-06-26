# Externs

The ClojureScript compiler optimizes names by replacing them with shorter names.  This makes for much smaller Javascript files, minimising the time it takes to load them. 

This type of optomisation works very well for your own Clojurescript, however it can cause problems when optomising Javascript libraries.

By specifying Externs for your project you tell the Clojurescript compiler which parts of your project are unsafe to optimize.

* [Clojurescript Externs - LispCast](http://www.lispcast.com/clojurescript-externs)

