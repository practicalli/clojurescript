# Theory: ClojureScript platforms

ClojureScript can be developed and deployed to three main platforms

![ClojureScript platforms](/images/clojurescript-platforms.png)

## Browser JavaScript Engine

Modern browsers all contain a JavaScript Engine and are a platform for front-end ClojuresScript apps.  For example, single page apps like react.js.


### Source maps

Browsers also provide inspection for your Clojurescript within the Browser.  Sourcemaps provide a link from the running JavaScript to the ClojureScript that generated it.  If you receive an error or are debugging you will see the relevant ClojureScript code (rather than have to work with the generated JavaScript).

### Google Closure compiler & tools

As ClojureScript used the [Google Closure compiler]() to generate JavaScript, then you can set options to generate JavaScript that will run on many browsers (even back to IE 6).


## NodeJS

NodeJS is a server-side application that can act as web application server for your ClojureScript applications

You can also connect to a ClojureScript REPL for your application running on NodeJS


### Compiling ClojureScript with NodeJS

work in progress


## Java Nashorn

The Java platform also includes a JavaScript engine called [Nashorn](https://en.wikipedia.org/wiki/Nashorn_(JavaScript_engine)).

Nashorn is not widely used for ClojureScript development or deployment.  However, it could be useful if you do not have access to node.js or a browser environment.

Nashorn is developed as part of the Java Open JDK and is advertised as a much faster JavaScript engine than the previous [Rhino](https://en.wikipedia.org/wiki/Rhino_(JavaScript_engine)) project.


## Vert.x

???
