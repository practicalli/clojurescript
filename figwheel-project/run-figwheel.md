# Run Figwheel

At this point make sure you are in the project root directory `hello_figwheel` and run Figwheel as follows:

```
lein figwheel
```

You should see a bunch of clojure libraries get downloaded and installed into your local maven repository (which happens to be in `~/.m2` on my Mac).

After that Figwheel will start up, compile your `hello-seymore.core` library and try to start a repl, BUT THE REPL WILL NOT START. Sorry for the caps, but this behavior is expected.

Type **Ctrl-C** to quit the Figwheel process.

If you list your project directory you should see this:
```
$ ls
figwheel_server.log
index.html
main.js
out
project.clj
src
target
```

Some new files have been created. The `main.js` file and the `out` directory contain your compiled ClojureScript code.

If you look at the contents of `main.js` you will see:

```
if(typeof goog == "undefined") document.write('<script src="out/goog/base.js"></script>');
document.write('<script src="out/cljs_deps.js"></script>');
document.write('<script>if (typeof goog != "undefined") { goog.require("hello_seymore.core"); } else { console.warn("ClojureScript could not load :main, did you forget to specify :asset-path?"); };</script>');

document.write("<script>if (typeof goog != \"undefined\") { goog.require(\"figwheel.connect\"); }</script>");
```

The last line of `main.js` loads the code that will connect to the Figwheel server. This is what enables the Figwheel server to communicate with the application, which is running in the browser.

