# Theory: Maps

A map in Clojure is a collection of key & value pairs in the form `{key value}`.  This kind of map is often referred to as a hash map in other languages.

Typically a `:keyword` is used for the keys in a map as this provides a simple way to extract values (keywords act like a function call that returns the value they are associated with in the map)

Values can be of any type, just like in other Clojure collections.  Values can also be defined as function calls or other collections including maps.

```
{:key "value"}
(:key 42)
{:key :value}
{"key" "value"}
("key" :value)

{:a 1 :b 2 :c 3 }
```

## Maps of Maps

Its common to have maps made up of other maps.  Here is an example of a map made up of a :keyword as the key and a map as the value.  The map representing the value is itself
;; defined with :keywords and strings

```
{:starwars {
    :characters {
      :jedi   ["Luke Skywalker"
               "Obiwan Kenobi"]
      :sith   ["Darth Vader"
               "Darth Sideous"]
      :droids ["C3P0"
               "R2D2"]}
    :ships {
      :rebel-alliance  ["Millenium Falcon"
                        "X-wing figher"]
      :imperial-empire ["Intergalactic Cruser"
                        "Destroyer"
                        "Im just making these up now"]}}}
```


Individual starwars characters can be defined using a map of maps

```
{:luke   {:fullname "Luke Skywarker" :skill "Targeting Swamp Rats"}
  :vader  {:fullname "Darth Vader"    :skill "Crank phone calls"}
  :jarjar {:fullname "JarJar Binks"   :skill "Upsetting a generation of fans"}}
```

To make the starwars character information easier to use, lets give the collection of characters a name using the def function

```
(def starwars-characters
   {:luke   {:fullname "Luke Skywarker" :skill "Targeting Swamp Rats"}
    :vader  {:fullname "Darth Vader"    :skill "Crank phone calls"}
    :jarjar {:fullname "JarJar Binks"   :skill "Upsetting a generation of fans"}})
```

Using the get function we return all the informatoin about Luke

```
(get starwars-characters :luke)
```


By wrapping a second `get` function around our first, we can get a specific piece of information about Luke

```
(get (get starwars-characters :luke) :fullname)
```

There is also the get-in function that makes the syntax a little easier to read

```
(get-in starwars-characters [:luke :fullname])
(get-in starwars-characters [:vader :fullname])
```

You can write more concise code by using the map or keywords as a function call on the data structure

```
(starwars-characters :luke)
(:fullname (:luke starwars-characters))
(:skill (:luke starwars-characters))

(starwars-characters :vader)
(:skill (:vader starwars-characters))
(:fullname (:vader starwars-characters))
```

And finally we can also use the threading macro to minimise our code further

```
(-> starwars-characters
    :luke)

(-> starwars-characters
    :luke
    :fullname)

(-> starwars-characters
    :luke
    :skill)
```

See the following [gist](https://gist.github.com/john2x/e1dca953548bfdfb9844) for more examples of destructuring with Clojure


## Duplicates in  following maps...

It is possible to have duplicate values in a map, but its not possible to have duplicate keys.  Any key must be unique within the scope of a map.

The following maps will throw duplicate key errors

```
{"fish" "battered" "chips" "fried" "fish" "battered and fried"}
{:fish "battered" :chips "fried" :fish "battered & fried"}
```

Duplicate values are okay though

```
{"fish" "battered" "chips" "fried" "cod" "fried"}
```

The same key can be used in a nested map.  For example, if a map has a keyword of `:name` and that key has a value defined by a map, then that map can also use the key `:name`.

```
{:name {:name "john" :address "London"}}
```

# Changing Maps

Maps are immutable, however you can 

```
(def alphabet-soup {:a 1 :b 2 :c 3})

(assoc alphabet-soup :d 4)
```
