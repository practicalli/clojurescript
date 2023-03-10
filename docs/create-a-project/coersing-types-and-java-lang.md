# Theory: Specifying Types & java.lang

Clojure has types that are created dynamically when the code is compiled, with everything being represented by Java objects as its compiled to Java bitecode.   However you do not need to specify any specific types as Clojure simply infers the type and handles most type collision gracefully.  The built in collections (list, map, vector & set) also support mixed types too.

In our project we are using Jetty, a web application server written in Java.  As its Java it needs a specific type of object passed as an argument for the port number, in this case an Integer.  However, when we run the Clojure project, the argument we supply for the port number on the command line is treated as a String object.  Therefore we need to change the port number from a Java String type to an Java Integer type.
  
The `java.lang.` library is part of all Clojure projects, so as we are going to create a Java Integer it makes sense to simply use the `Integer` constructor with a String argument which returns a new Integer object.

The `Integer. port-number` Clojure code is a short-hand for calling the `java.lang.Integer` constructor.  The `.` is actually a macro in Clojure that provides a simple way to work with Java, allowing you to call Java objects as if they were Clojure functions.  In Java you would have to use the form `Type instance-name = new Type(argument)`.  In our example you would write this in Java as `String port = new String(port-number)`

> **Hint**  From the [Java 8 docs for Integer class](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html):   
`Integer(String s)` - constructs a newly allocated Integer object that represents the int value indicated by the String parameter.

## Theory: Its Java Objects underneath strings & numbers

Strings and numbers are represented by Java objects underneath, so its convienient to use Java Classes to manipulate these simple data structures on the rare occasion you need a specific type.  

You can see the underlying Java types in Clojure using the `type` or `class` function.  In the following example you can see the Java types for strings and numbers

![Clojure Types: String to Integer examples](/images/clojure-types-examples-string-to-integer.png)
