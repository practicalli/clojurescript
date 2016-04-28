# Data Structures


When you define a name for a persistent data structure (list, map, vector, set), that name is termed a `Var`.  A var is a mutable reference that points to the data structure.  A Var is mutable, because it can be changed to point to another data structure (or any other legal Clojure expression)

When you pass a name as an argument to a function, you are passing a reference to a data structure.  If that function modifies that data structure, it will create a new data structure and pass that back by value.

The new data structure may include references to the original data structure if they have common values, an in-memory sharing model that makes persistent data structures very efficient in terms of memory use.

Persistent data structures are held in memory as binary tree of values - TODO: how does this look for the different persistent data structures (eg. is the node value for a map the key & value)
