# Reloadable Code

Writing reloadable code in Clojure and ClojureScript is highly recommended to support the REPL workflow and reload code without adversely affecting the behavior of the system.

Reagent and similar ClojureScript libraries strongly encourage a code design conducive to code reloading,

Reloadable code by nature is more robust and maintainable.

Three key concepts:

- idempotent functions
- define initial state once
- logical code segregation.

<!-- TODO: update code examples -->

## Idempotent Functions

An Idempotent function has the same effect whether it is called once or many times.

All functions that are reloaded should be idempotent, otherwise unpredictable side effects may occur on every reload

For instance, a function that sets the innerHTML property of a DOM element is idempotent, but a function that appends a child to some other element is not:

!!! EXAMPLE "Idempotent vs Non-Idempotent Functions"
    ```clojure
    (defn append-element [parent child]   ;; (1)!
      (.appendChild parent child))

    (defn set-content [element content]      ;; (2)!
      (set! (.-innerHTML element) content))
    ```

    1. Non-idempotent function
    2. Idempotent function


`append-element` function is not idempotent as the `parent` value is modified by the `child` each time.

`set-content` function is idempotent as `element` is set each time so the result is going to be the same.


!!! EXAMPLE "Idempotent append-element function"
    ```clojure
    (defn append-element [parent child]
      (when-not (.contains parent child)
        (.appendChild parent child)))
    ```


## Define Initial State Once

State values that change whilst the application is running should define the initial start state values so they are evaluated only once (per REPL session)

[`defonce`](https://clojuredocs.org/clojure.core/defonce){target=_blank} is a clojure.core macro that wraps the `def` behaviour to ensure its value is only evaluated if it has not yet been evaluated (has no root in the namespace)

Figwheel-main templates that use Reagent typically use an atom to manage the state and this is defined using a `defonce` form.

Using `defonce` for the app-state ensures the app-state is not reset to the initial state each time a change is saved and triggers Figwheel-main to reload the code.  Even if the value defined by `defonce` is changed and evaluated, the new value will not be used

!!! EXAMPLE "Figwheel-main app-state for Reagent"
    ```clojure
    (defonce app-state (atom {:text "Hello world!"}))
    ```

!!! HINT "Hack a change to the app-state"
    Change `defonce` to `def` will allow the value of app-state to be evaluated again, if the initial app-state really needs to change.

    `(swap! ,,,)` or `(reset!)` in a `(comment ,,,)` rich comment blog is the common approach to changing or resetting the app-state
    ```clojure
    (comment
    (deref app-state)  ;; (1)! View the current app-state value
    (swap! app-state assoc :text "Modified app-state value") ;; (2)! Change the app-state value
    (reset! app-state {:text "Reset app-state value"}) ;; (3)! Change the app-state value
    )
    ```
    1. View the contents of the app-state atom
    2. Associate (add to) the value contained in the app-state atom. Use update instead of assoc to change an existing value
    3. Reset the app-state value, typically to a known start state value


## Define Initialisation Code Once

[`defonce`](https://clojuredocs.org/clojure.core/defonce){target=_blank} can be used to protect initialization code from running repeatedly.

A defonce expression takes the form: (defonce name expr) where name is a symbol that names the var to bind and expr is any ClojureScript expression. Not only does defonce prevent the var from being redefined, it also prevents expr from being re-evaluated when the var is bound. This means that we can wrap initialization code with a defonce to guarantee that it will only be evaluated once, regardless of how often the code is reloaded:

!!! EXAMPLE "Wrap Initialisation Code to run only once"
    ```clojure
    (defonce initialised?
      (do                                                      ;; (1)!
        (.setItem js/localStorage "init-at" (.now js/Date))
        (js/alert "Initialising System Configuration!")
        true))                                                 ;; (2)!
    ```

    1. do can evaluates multiple expressions in turn, returning the resutl of evaluating the last expression
    2. `initialised?` uses the `?`predicate name form, so a boolean value is returned by convention


`initialised?` is only evaluated once and bound to the value `true` once initialisation is complete.

[`do`](https://clojuredocs.org/clojure.core/defonce){target=_blank} evaluates each expression in turn and returns the value of the final expression.  The expressions before the last typically have side effect, e.g. setting local storage, logging, alerts, etc.


## Logical Grouping

New projects typically start with a single Clojure namespace and a few functions.  As the project grows, new namespaces can be defined to logically separate the different aspects of the application.

Examples of logical namespace groups can include

- View of information
- data transformation
- domain (e.g. business) rules
- communication with the outside word (databases, message systems, UI, APIs, etc.)

As code grows, its also important to ensure that function definitions do not become convoluted in their behaviour.  Each function should do one specific thing and where possible be pure and idempotent.

In a messaging system (chat, email, social, etc), define a function to append a new message to a feed.

!!! EXAMPLE "Convoluted function to recieve and add message to feed"
    The function design does not separate the logic of receiving a new message from displaying it:
    ```clojure
    (defn message [text date-time]
      (let [node (.createElement js/document "div")]
        (set! (.- innerHTML node) (str "[" date-time "]: " text))
        (.appendChild messages-feed node)))
    ```

Should the user interface api no longer require the date-time information, the `message` function also requires a refactor.

Refactor the code to hold the messages in an atom which is empty to start with.  Split the `message` function by its logical concerns.

!!! EXAMPLE "Separation of concerns"
    ```clojure
    (defonce messages (atom []))           ;; (1)!

    (defn message [text timestamp]         ;; (2)!
      (swap! messages conj
      {:text text :timestamp timestamp}))

    (defn publish! [messages]              ;; (3)!
      (set! (.- innerHTML messages-feed) "")
      (doseq [message @messages]
        (let [node (.createElement js/document "div")]
          (set! (.-innerHTML node) (str "[" timestamp "]: " text))
          (.appendChild messages-feed node))))

    (comment
      (publish!))                          ;; (4)!
    ```

    1. Incoming messages are stored in an atom which is defined once (per REPL sesison)
    2. `message` is a business logic function
    3. `publish!` is view logic function
    4. Use rich comment to publish messages to the feed

Reagent and similar frameworks will automatically trigger publish! updates when the data being managed changes.
