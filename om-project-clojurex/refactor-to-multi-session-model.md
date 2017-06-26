# Refactor To Multi Session Model

It would be a very short conference if there were only one session, so lets use the data model that holds multiple sessions

> #### Note::Model multiple sessions
> Update the model for the conference session to hold multiple sessions

<!--sec data-title="Reveal answer..." data-id="answer002" data-collapse=true ces-->

A parent map is added to the model with a key called `:sessions` pointing to a vector.  Each session is an element of this vector

Modelling an empty collection of sessions

```clj
{:sessions []}
```

Modelling a collection with one session

```clj
{:sessions [{:title "Opening Keynote"
             :description "Something very inspirational"
             :speaker-name "John Stevenson"
             :speaker-biography "There's a frood who really knows where his towel is."
             :twitter-handle "jr0cket"
             :github-handle "jr0cket"
             :speakers-website "http://jr0cket.co.uk"}]}
```

Refactor the example session to give it a name

```clj
(def john {:title "Opening Keynote"
           :description "Something very inspirational"
           :speaker-name "John Stevenson"
           :speaker-biography "There's a frood who really knows where his towel is."
           :twitter-handle "jr0cket"
           :github-handle "jr0cket"
           :speakers-website "http://jr0cket.co.uk"})
```

Now use that name inside the collection of sessions to make the example data easier to work with

```clj
{:sessions [john]}
```

<!--endsec-->

> #### Hint::
> A common way to create a collection of things in Clojure is to use a vector, `[]`.
