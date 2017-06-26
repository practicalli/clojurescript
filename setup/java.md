## Java

  You will need to have a Java Runtime Edition (usually installed on most computers by default) to run any Clojure applications.

  Check you have a Java runtime on your system path by typing the following in a terminal window:
  
```bash
java -version
```

## Install Java

If Java is not found, please install it from [Oracle](http://www.oracle.com/technetwork/java/javase/downloads/index.html) or [OpenJDK](http://openjdk.java.net/projects/jdk8/).  

Java may also be available via your operating systems package manger, for example on Ubuntu / Debian systems this would be installed via sudo apt-get install openjdk-8-jre`


> **Hint** ClojureScript uses the Google Closure compiler and build tools that require a Java Virtual machine.  However, work is in progress to make ClojureScript self hosting.  See articles such as [ClojureScript Next](http://swannodette.github.io/2015/07/29/clojurescript-17/) and [Bootstrapped ClojureScript FAQ](https://github.com/clojure/clojurescript/wiki/Bootstrapped-ClojureScript-FAQ) for pro's and con's of this approach.
