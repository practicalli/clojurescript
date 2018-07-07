# Interact with the REPL evaluate code

Evaluating code in the REPL directly is useful for testing quick changes to your application, so its very useful for changing the `app-state` and seeing the results.

Any code you enter in the REPL directly that you want to use again can be added to the source code file as a comment.

> #### Note::Update the :text in `app-state`
> In the repl, update the string value that is associated with :text in the map inside the `app-state` atom.
>
> The [swap!]() function is used to update the value of an atom.
> The [assoc]() function can be used to create a new value in a map

<!--sec data-title="Reveal answer..." data-id="answer001" data-collapse=true ces-->

```clojure
(swap! app-state assoc :text "Evaluating code in the REPL is fun")
```

<!--endsec-->
