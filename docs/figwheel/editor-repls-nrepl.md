# Editor REPLs & nREPL


You may want a REPL in your editor. This makes it much easier to ship code
from your buffer to be evaluated.

> If you use `lein repl` or something that invokes it like CIDER, you
> are using nREPL. A ClojureScript REPL will not just run over an nREPL
> connection without Piggieback.

If you are just starting out I would use the Figwheel console REPL because it's
aready set up and ready to go, complexity conquered!

If you want to integrate a REPL into your editor, here are my top
recommendations:

**Emacs**:
* use `inf-clojure` as described on the [wiki page](https://github.com/bhauman/lein-figwheel/wiki/Running-figwheel-with-Emacs-Inferior-Clojure-Interaction-Mode)
* alternatively use [Cider and nREPL](https://github.com/bhauman/lein-figwheel/wiki/Using-the-Figwheel-REPL-within-NRepl). *Using the ClojureScript REPL over an nREPL connection is considered advanced*

**Cursive**: use the instructions on the [wiki page](https://github.com/bhauman/lein-figwheel/wiki/Running-figwheel-in-a-Cursive-Clojure-REPL)

**Vi**: use `tmux` mode to interact with the figwheel REPL, still trying to get a wiki page for this if you can help that would be great

If you are going to use nREPL with Figwheel please see:

[Using Figwheel within NRepl](https://github.com/bhauman/lein-figwheel/wiki/Using-the-Figwheel-REPL-within-NRepl)
