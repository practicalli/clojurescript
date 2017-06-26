# Om Cursors

Cursors are a fundamental part of Om. They let components refer to pieces of the app state without knowing where they are in the state tree.

A cursor is an atom and a path to a specific part of the data structure inside that atom.  For example, a cursor would be:

* [app-state :sessions] - a cursor pointing to the whole of the session data
* [app-state :sessions 0] - a cursor pointing to the first session in the collection of sessions
* [app-state :sessions 2 :title] - a cursor pointing to the third session's title

## Om/update!

call om/update! with the cursor and the part of the model to update then the app-state will be updated in the correct place.

## om/transact!

A component doesn’t know exactly where in the app state data tree its data comes from. It’s the cursor‘s job to keep track of that. The cursor also lets you modify the data in the app state atom without knowing where it is. You do that with `om/transact!`.

`om/transact!` needs the cursor as the first argument. The second argument is a key to grab a subvalue from the cursor. So if the current value of the cursor is {:name "Samantha" :favourite-colour "Green"}, you can grab just the name by calling `transact!` with the key `:name`. That means the function will just be called with the string "Samantha" and work on only that part of the model.


