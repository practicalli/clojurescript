# Adding Session Data to State

Use the sessions defined for `john`, `kris` and `bug` and add them to the state.

> #### Note::Add sessions to the state
> Using the names of the session we just defined, add the sessions to the state using the REPL or add to the `core.cljs` and evaluate the code.
>
> Use the [swap!](https://clojuredocs.org/clojure.core/swap!) function to update the `app-state`.  See the section on [interacting with the REPL](interact-with-project.html)
>
> The [update](https://clojuredocs.org/clojure.core/update) function can be used to add values to an existing key.

<!--sec data-title="Reveal answer..." data-id="answer00" data-collapse=true ces-->

```clj
(swap! app-state update :sessions conj john)

(swap! app-state update :sessions conj kris)

(swap! app-state update :sessions conj bug)
```
<!--endsec-->


> #### Hint::
> Using the comment reader macro, `#_`, you can add code to your Clojurescript file for test the application and avoid that code being evaluated each time the file is saved.
>
> Placing your cursor at the end of the expression will allow you to evaluate it in your editor, even though it is commented out.
> 
> If the state gets messy or something goes wrong, then you can also reset the state:
>
> `(reset! app-state {:conference-name "ClojureX" :sessions []})`
