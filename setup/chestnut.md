# Chestnut

![Chestnut](/images/chestnut.png)

[Chestnut](https://github.com/plexus/chestnut) is a Leiningen template for a ClojureScript app based on Om, featuring a great dev setup, and easy deployment.

For smooth development you get instant reloading of Clojure, ClojureScript, and CSS. A browser-connected REPL is also included.

For deployment you get uberjar support, meaning you can get all your code compiled, optimized, and packaged in a single executable JAR file. It also contains the necessary artifacts to work on Heroku out of the box.

Need help? Ask on the [mailing list](http://chestnut.aren.io/)


## Chestnut 0.9.0-SNAPSHOT

A major update is in the works. To try it out, use `lein new chestnut my-project --snapshot`.

* Use Figwheel for REPL and Ring server
* Remove boilerplate that's no longer needed
* Drop Enlive and simplify the dev setup
* Drop CLJX support
* Better inline documentation

## Usage

```
lein new chestnut <name>
```

After that open the README of your generated project for detailed
instructions.

## Command line

```
$ lein repl

(run)
(browser-repl)
```

Wait a bit, then browse to
[http://localhost:10555](http://localhost:10555).

### Lighttable

Lighttable provides a tighter integration for live coding with an inline browser-tab. Rather than evaluating cljs on the command line with weasel repl, evaluate code and preview pages inside Lighttable.

Steps: After running `(run)`, open a browser tab in Lighttable. Open a cljs file from within a project, go to the end of an s-expression and hit Cmd-ENT. Lighttable will ask you which client to connect. Click 'Connect a client' and select 'Browser'. Browse to [http://localhost:10555](http://localhost:10555)

View LT's console to see a Chrome js console.

Hereafter, you can save a file and see changes or evaluate cljs code (without saving a file). Note that running a weasel server is not required to evaluate code in Lighttable.

### Emacs/Cider

Start a repl in the context of your project with `M-x cider-jack-in`.

Switch to repl-buffer with `C-c C-z` and start web and figwheel servers with `(run)`, and weasel server with `(browser-repl`). Load [http://localhost:10555](http://localhost:10555) on an external browser, which connects to weasel, and start evaluating cljs inside Cider.

## List of Contents

This template gives you everything you need to start developing
Clojure/ClojureScript apps effectively. It comes with

* [Figwheel](https://github.com/bhauman/lein-figwheel) Automatically
  reload your ClojureScript and CSS as soon as you save the file, no
  need for browser refresh.
* [Om](https://github.com/swannodette/om) ClojureScript interface to
  Facebook's React.
* [Ring](https://github.com/ring-clojure/ring) Clojure's de facto HTTP
  interface. Chestnut uses a Jetty or HttpKit server to serve the
  Clojurescript app. This way you already have an HTTP server running
  in case you want to add server-side functionality. Chestnut also
  inserts a Ring middleware to reload server-side Clojure files.
* Heroku support. Chestnut apps have all the bits and pieces to be
  deployable to Heroku. Getting your app on the web is as simple as
  `git push`.
* Unit tests for both Clojure and CLJS. Or you can decide to use Speclj instead, both for CLJ and CLJS.
  Both specs and CLJS tests can be run in "auto" mode.

## Options

* `--http-kit` Use [HTTP Kit](http://http-kit.org/server.html) instead
  of Jetty
* `--site-middleware` Use the `ring.middleware.defaults.site-defaults` middleware
  (session, CSRF), instead of `ring.middleware.defaults.api-defaults` (see
  [ring.defaults documentation](https://github.com/ring-clojure/ring-defaults))
* `--om-tools` Use Prismatic's
  [om-tools.dom](https://github.com/Prismatic/om-tools) instead of
  `om.dom`
* `--less` Use [less](https://github.com/montoux/lein-less) for
  compiling Less CSS files.
* `--speclj` Use [speclj](http://speclj.com) test runner for clj and
cljs, and disable the core cljs.test tests.

Use `--` to separate these options from Leiningen's options,
e.g. `lein new chestnut foo -- --om-tools --http-kit`

## Local copy

If you want to customize Chestnut, or try unreleased features, you can
run directly from master like this:

``` sh
git clone https://github.com/plexus/chestnut.git
cd chestnut
lein install
```

Note that master may be partially or wholly broken. I try to do
extensive manual testing before releasing a new stable version, so if
you don't like surprises then stick to the version on Clojars. Issue
reports and pull requests are very welcome.

