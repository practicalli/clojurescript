# Using the REPL

Since all code evaluated in the REPL actually runs on the browser, we have some powerful tools at our disposal. For example, we can take our `app-state` to places our UI interface can't easily reach to test for edge cases. Imagine that there might be a problem when the counter displays a 5 digit number after a number of things happened. Would you do those things and then click 10000 times on "Thumbs up"?

> ##### Pro-tip: use rlwrap
> You'll get a much better REPL experience if you install [rlwrap](https://github.com/hanslub42/rlwrap) and run `rlwrap lein figwheel`
>
> you can install `rlwrap` on OSX with `brew install rlwrap`

Start the REPL and go to the `hello-seymore.core` namespace

```clojure
> (in-ns 'hello-seymore.core)
nil
```

Then change `app-state` to whatever number you want to test and check it on the browser:

```clojure
> (reset! app-state {:likes 10000})
{:likes 10000}
```

