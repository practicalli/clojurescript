# Defining Session Data

Now we can display multiple sessions, lets define some more sessions so we have more test data to experiment with.

Here is the full set of sample session data, with each session 

```clj
(def john {:title "My Spacemacs Obsession"
           :description "Feel the power of Emacs, without the RSI"
           :speaker-name "John Stevenson"
           :speaker-biography "There's a frood who really knows where his towel is."
           :twitter-handle "jr0cket"
           :github-handle "jr0cket"
           :speakers-website "http://jr0cket.co.uk"})

(def kris {:title "Opening Keynote"
           :description "Something very inspirational"
           :speaker-name "Kris Jenkins"
           :speaker-biography "The most fantastically dressed developer in the world"
           :twitter-handle "krisajenkins"
           :github-handle "krisajenkins"
           :speakers-website "http://krisajenkins.co.uk"})

(def bug {:title "A Glass of CIDER"
          :description "Unleashing the power of Clojure with Emacs"
          :speaker-name "Bozhidar Batsov"
          :speaker-biography
          "Bozhidar is the maintainer of CIDER and the editor of the community Clojure style guide. Most people would probably describe him as an Emacs zealot (and they would be right). He's also quite fond of the Lisp family of languages, functional programming in general and Clojure in particular. Believe it or not, Bozhidar has hobbies and interests outside the realm of computers, but we won't bore with those here."
          :twitter-handle "bbatsov"
          :github-handle "bbatsov"
          :speakers-website "http://batsov.com/"})
```

> #### Hint::
> `clojure.spec` can be used to define your test data and functions that work on that data to give you a testable specification for your application.
>
> https://clojure.org/guides/spec
