# Run Figwheel again


Now run Figwheel again:

```
$ lein figwheel
```

and load the `index.html` in the browser **from the filesystem**. The location bar in your browser should have a `file://<...>/hello_seymore/index.html` url in it.

Change back to the terminal where Figwheel is starting and **when it finishes** you should see a REPL prompt.  

Go ahead and type some ClojureScript at the REPL prompt:
```clojure
=> (+ 1 2 3)
6
```

If you get `6` as a response then you have successfully set up Figwheel!!!

You can also see that the REPL is connected to the browser:

```clojure
=> (js/alert "Am I connected to Figwheel?")
nil
```

You should see the alert in the browser window. Only after you click on "Ok" there, will the REPL return `nil`.

Also, go ahead and open up the browser's dev tools so you can see the messages from Figwheel. You should see something like this (in Chrome):

![Figwheel messages in the console](http://rigsomelight.com/assets/images/figwheel-starting-output.png)

Now go back to your `src/hello_seymore/core.cljs` file and change the line that looks like:

```clojure
(.log js/console "Hey Seymore sup?!")
```
to
```clojure
(.log js/console "Hey Seymore! wts goin' on?")
```
and save the file. You should now see `Hey Seymore! wts goin' on?` printed in the dev console of your browser.

Congratulations!! You have set up Figwheel and your code is getting loaded into the browser as you save it.

As you can see, side-effects from print functions happen on every reload. This might not be desirable for all side-effects. Code that only triggers desired side-effects is called "reloadable code". We will discuss how to write such code later. Please remember that you are responsible for writing reloadable code! :)

> ##### Pro-tip: tail the figwheel_server.log
> When working with Figwheel you should really have a separate terminal open to watch the
> `figwheel_server.log`. This can be immensely helpful when things aren't working correctly.
>
> So open another terminal and type: `$ tail -f figwheel_server.log`

