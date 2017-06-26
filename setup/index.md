# Setup

This workshop requires a few tools to be present in your development environment to start with:

| Tool                                                                                      | Version | Test install (command line) |
|-------------------------------------------------------------------------------------------|---------|-----------------------------|
| [Java JRE or Java SE](http://www.oracle.com/technetwork/java/javase/downloads/index.html) |       8 | `java -version`             |
| [Leiningen](http://leiningen.org/)                                                        |   2.7.1 | `lein version`              |
| [Git Client](https://git-scm.com/)                                                        |     2.x | `git --version`             |

> **Hint** To install any of these tools, see the instructions later on in this article.

> Clojure & ClojureScript are installed as libraries by Leiningen, so do not need to be installed directly.


## Clojure Aware Editors

I recommend using a Clojure aware editor with REPL for the workshop, so you can follow the code and use structural editing features to navigate the code.

| Background                                                                 | Recommended Editor                                 |
|----------------------------------------------------------------------------|----------------------------------------------------|
| Java / [Intellij]()                                                        | [Cursive](https://cursive-ide.com/)                |
| Web Developer using [Atom](https://atom.io)                                | [Protorepl](https://atom.io/packages/proto-repl)   |
| Polyglot developer using [Emacs](http://www.gnu.org/software/emacs/) / Vim | [Spacemacs](https://github.com/syl20bnr/spacemacs) |
| Developer with custom Emacs config                                         | [CIDER](https://github.com/clojure-emacs/cider)    |
| You just want something simple                                             | [LightTable](http://lighttable.com/)               |

I recommend using Emacs with Spacemacs and have a detailed workshop on how to get the most out of [Spacemacs for Clojure development](https://practicalli.github.io/spacemacs/).

> **Hint** Clojure & ClojureScript are installed as libraries by Leiningen

If any of the above are missing, then the rest of this setup section will help you get your local developer environment configured.


## Clojure / Clojurescript

There is no specific install for Clojure.  Clojure comes as a library, a JAR file, managed by the build tool Leiningen just like any other dependency.

When you create a project with Leiningen, the configuration is created in a file called `project.clj`.  Inside this `project.clj` is a `dependencies` entry where the version of clojure is specified along with any other dependencies.  Here is an example of a `project.clj` configuration with just Clojure as a dependency

```
(defproject project-name "0.1.0-SNAPSHOT"
  :description "FIXME: write description"
  :dependencies [[org.clojure/clojure "1.8.0"]
                 [org.clojure/clojurescript "1.9.89"]])
```
  
> **Hint** The Clojure library is very small (~3.6Mb) and Clojurescript is a tiny 695k.  Leiningen caches it and all other libraries locally, using the same folder structure that Maven uses, eg  Clojure version 0.1.89 would be cached in ` ~/.m2/repository/org/clojure/clojurescript/0.1.98/`
