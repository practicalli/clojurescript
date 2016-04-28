# Google Closure

In order to abstract away JavaScript environment differences ClojureScript relies on the [Google Closure Library](https://developers.google.com/closure/library/) (GCL). GCL supplies an important facility missing from JavaScript: namespaces and a way to declare dependencies between them. In fact ClojureScript namespaces get compiled to Google Closure namespaces.

Loading dependencies correctly across various browser targets is a surprisingly tricky affair. GCL accomplishes this by maintaining a
dependency graph. When you require a namespace it will write the needed script tags in dependency order for you.

So what went wrong? If you look at `out/main.js` you will see some dependency graph building calls:

```js
goog.addDependency("base.js", ['goog'], []);
goog.addDependency("../cljs/core.js", ['cljs.core'], ...);
goog.addDependency("../hello_world/core.js", ['hello_world.core'], ...);
```

But wait, where is this `goog` object coming from?

Oops. We never loaded it! In order for GCL to bootstrap we must
at least load `goog/base.js`. You'll see this is available in
`out/goog/base.js`. Let's add this to your page now:

```html
<html>
    <body>
        <script type="text/javascript" src="out/goog/base.js"></script>
        <script type="text/javascript" src="out/main.js"></script>
    </body>
</html>
```

Refresh the page.

The error will be gone but you still won't see the desired `"Hello
world!"`.

Hrm. `out/main.js` didn't appear to have any of the logic that we
wrote, in fact it only includes the needed dependency graph
information for the ClojureScript standard library `cljs.core` and our
namespace.

Ah. The last step we missed was actually requiring our namespace to
kick things off. Change `index.html` to the following.

```html
<html>
    <body>
        <script type="text/javascript" src="out/goog/base.js"></script>
        <script type="text/javascript" src="out/main.js"></script>
        <script type="text/javascript">
            goog.require("hello_world.core");
            // Note the underscore "_"! 
        </script>
    </body>
</html>
```

Refresh your `index.html` and you should finally see `"Hello world!"` printing to the browser JavaScript console. If you're using a
sufficiently modern browser you should even see the printing was invoked from a ClojureScript source file and not a JavaScript one
thanks to source mapping (some browsers like Chrome require you to first enable source mapping, for more details [look here](https://developer.chrome.com/devtools/docs/javascript-debugging#source-maps)).
