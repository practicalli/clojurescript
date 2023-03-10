## Testing

Tests can be written using `clojure.test` and `clojurescript.test`, which are both built into the language.

https://clojurescript.org/tools/testing

> **fixme** This section needs expanding upon

To run the Clojure tests, use
  
``` shell
lein test
```

To run the Clojurescript you use [doo](https://github.com/bensu/doo).

Doo can run your tests against a variety of JavaScript implementations, but in the browser and "headless". For example, to test with PhantomJS, use

``` shell
lein doo phantom
```

