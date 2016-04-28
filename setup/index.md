# Setup

This workshop requires a few tools to be present in your development environment:

  * Java 8 runtime environment (JRE) - test with `java -version` in a command line window
  * [Leiningen](http://leiningen.org/) version 2.5.3 - test with `lein version` in a command line window
  * [Figwheel]() - a Leiningen plugin (should be added to ~/.lein/profiles.clj)
  * A Clojure aware editor with REPL
    - [LightTable](http://lighttable.com/)
    - [Emacs](http://www.gnu.org/software/emacs/) with [Spacemacs](https://github.com/syl20bnr/spacemacs) or [CIDER](https://github.com/clojure-emacs/cider)
    - Atom
    - Sublime
  * A [Git client](http://git-scm.com/)

> **Hint** Clojure & ClojureScript are installed as libraries by Leiningen

If any of the above are missing, then the rest of this setup section will help you get your local developer environment configured.

## Java 
  Check you have a Java runtime on your system path by typing the following in a terminal window:
  
```bash
java -version
```

If Java is not found, please install it from [Oracle](http://www.oracle.com/technetwork/java/javase/downloads/index.html) or [OpenJDK](http://openjdk.java.net/projects/jdk8/).  Java may also be available via your operating systems package manger, for example on Ubuntu / Debian systems this would be installed via `sudo apt-get install openjdk-8-jre`

> **Hint** ClojureScript uses the Google Closure compiler and build tools that require a Java Virtual machine.  However, work is in progress to make ClojureScript self hosting.  See articles such as [ClojureScript Next](http://swannodette.github.io/2015/07/29/clojurescript-17/) and [Bootstrapped ClojureScript FAQ](https://github.com/clojure/clojurescript/wiki/Bootstrapped-ClojureScript-FAQ) for pro's and con's of this approach.

## Leiningen
  [Leiningen](http://leiningen.org/) is the most commonly used build automation tool used to manage Clojure projects.  Install by [saving the Leiningen install script](https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein) and running it inside a terminal window  

* [Install script for Linux & MacOSX](https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein)
* [Install script for Microsoft Windows](https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein.bat)


Save the file to somewhere on your operating system path, eg `~/bin`

```bash
chmod a+x ~/bin/lein
lein
```

 The first time you run this script it downloads a Java archive file (JAR) of the latest version of Leiningen.  When you run the script again, you have a working Leiningen build tool.


## Figwheel

Figwheel builds your ClojureScript code and hot loads it into the browser as you are coding!  Figwheel is installed as a Leiningen plugin and is typically setup using a leiningen template for ClojureScript.


## Development tools with Clojure support 

A tool that understands Clojure will help you write code faster and more accurately.  Here are a few common development tools used for Clojure

* [LightTable](http://lighttable.com/) - has an Instarepl that evaluates your code as you type, great for Clojure beginners
* [Emacs](http://www.gnu.org/software/emacs/)  with either [Emacs Live](https://github.com/overtone/emacs-live), [Spacemacs](https://github.com/syl20bnr/spacemacs) or [CIDER](https://github.com/clojure-emacs/cider) -  highly extensible support for Clojure, auto-completion, snippets, REPL & refactoring.
* [Nightcode](https://nightcode.info/) - good for beginers, nice Clojure on Android support
* [SublimeText](http://www.sublimetext.com/) - simple editor with basic Clojure awareness, used with `lein repl` on the command line


## Clojure 

There is no specific install for Clojure.  Clojure comes as a library, a JAR file, managed by the build tool Leiningen just like any other dependency.

When you create a project with Leiningen, the configuration is created in a file called `project.clj`.  Inside this `project.clj` is a `dependencies` entry where the version of clojure is specified along with any other dependencies.  Here is an example of a `project.clj` configuration with just Clojure as a dependency

```
(defproject project-name "0.1.0-SNAPSHOT"
  :description "FIXME: write description"
  :url "http://example.com/FIXME"
  :license {:name "Eclipse Public License"
            :url "http://www.eclipse.org/legal/epl-v10.html"}
  :dependencies [[org.clojure/clojure "1.7.0"]])
```
  
> **Hint** The Clojure library is very small (~3.7Mb) and Leiningen caches it and oll other libraries locally in the same folder structure that Maven uses, eg  Clojure version 0.1.7 would be cached in ` ~/.m2/repository/org/clojure/clojure/0.1.7/`
