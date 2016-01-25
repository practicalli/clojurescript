# ClojureScript, Practical.li

![Clojure logo](images/clojure-practicalli-banner.png)

This workshop is aimed at those new to writing client-side web applications using the ClojureScript programming language, a functional programming language based on Lisp and compiled to JavaScript.

ClojureScript and client side development are covered in a highly practical way, so you can evaluate where ClojureScript is useful in your own projects.

ClojureScript is a relatively new approach to development and whilst it has a great many advantages it also can require more tolerance to change, specifically in the tooling and libraries.  And we all have experienced the frequent change in the JavaScript world itself.

  This workshop guides you through the basics of client-side web development and helps you understand the modular approach to using ClojureScript effectively.  Along the way the relevant functions and design approaches common to ClojureScript will be highlighted.

> **Hint** This workshop is under heavy development and so please feel free to leave comments on anything that does not work, does not make sense or any ideas and topics that you think are missing.  The contents of this book has been written with markdown and is available via a [Github repository](https://github.com/practicalli/clojurescript-content) and of course pull requests are welcome.

## Requirements 

  * A working **Java 8** runtime environment (JRE) - test with `java -version` in a command line window
  * [Leiningen](http://leiningen.org/) version 2.5.3 - test with `lein version` in a command line window
  * A Clojure aware editor with REPL
    - [LightTable](http://lighttable.com/)
    - [Emacs](http://www.gnu.org/software/emacs/) with [Spacemacs](https://github.com/syl20bnr/spacemacs) or [CIDER](https://github.com/clojure-emacs/cider)
  * A [Git client](http://git-scm.com/)


  See the [setup](/setup/) section for details on how to get your environment ready

## Code for the workshop

> **Fixme** The code for this workshop has not yet been made public, sorry.

The code for this workshop is contained in the Github repository [ClojureScript example](https://github.com/practicalli/clojure-webapps-example), the code for each section is in a specific branch.

To get a copy of the repository, use the following git clone command which creates a new directory called clojure-webapps-example that contains the cloned code. 

`git clone https://github.com/practicalli/clojurescript-example.git`

Once you have the repository, use `git checkout branch-name` to get the code for each section.  Each branch is a working application with all the features covered in that section

Use `git branch` to show all the branches available, they should match the names of the sections in this workshop.

Enjoy.

## Additional Resources

**Workshop**
* [ClojureScript Unraveled](http://funcool.github.io/clojurescript-unraveled/)
* [The case for React.js & ClojureScript](http://www.slideshare.net/murilasso/the-case-for-reactjs-and-clojurescript)
* [Getting started with Clojure](http://jr0cket.co.uk/slides/getting-started-with-clojure.html) - a general guide to Clojure (work in progress)
* [Clojure through code](https://github.com/practicalli/clojure-through-code/tree/drafts) - many examples of basic Clojure code 


**Clojure**
* [Clojure.org](http://clojure.org), [features](http://clojure.org/features) and [rational](http://clojure.org/rationale)
* [ClojureScript home]()
* [Clojure documentation](http://clojure.org/documentation)
* [ClojureScript documentation](http://clojure.org/documentation)
* [ClojureScript cheetsheet](http://cljs.info/cheatsheet/)
* [Clojure cheetsheet](http://clojure.org/cheatsheet)


**Tooling**
* [Leiningen](http://leiningen.org/), [tutorial](https://github.com/technomancy/leiningen/blob/stable/doc/TUTORIAL.md), [faq](https://github.com/technomancy/leiningen/blob/stable/doc/FAQ.md), [plugins list](https://github.com/technomancy/leiningen/wiki/Plugins) & [sample project file](https://github.com/technomancy/leiningen/blob/stable/sample.project.clj)
  * [lein-figwheel](https://github.com/bhauman/lein-figwheel) - hot reload your code!
* [LightTable](http://lighttable.com/), [docs](http://docs.lighttable.com/), [blog](http://www.lighttable.com/blog/), [announcements](https://groups.google.com/forum/#!forum/light-table) and [discussions](https://groups.google.com/forum/#!forum/light-table-discussion).
* [ClojureScript REPL as a WebService](http://himera.herokuapp.com/index.html)
* [Emacs](https://www.gnu.org/software/emacs/) and [Spacemacs](https://github.com/syl20bnr/spacemacs/)
* [Chestnut Leiningen Template](https://github.com/plexus/chestnut)
* [Reagent Leiningen Template](https://github.com/reagent-project/reagent-template)
* [Bounce-webapp Leiningent Template](https://clojars.org/bounce-webapp/lein-template) - by James Henderson


**Community**
* [Clojure-docs](http://clojure-doc.org/) - community docs 
* [CrossCLJ](http://crossclj.info/) - cross-referencing the Clojure ecosystem
* [4Clojure](https://www.4clojure.com/) exercises & [4Clojure Google group](https://groups.google.com/forum/#!forum/4clojure)
* [London Clojurians](http://londonclojurians.org) and their [Google group](https://groups.google.com/forum/#!forum/london-clojurians)
* [ClojureScript Koans](http://clojurescriptkoans.com/)
* [Clojure & Clojurescript Slack channels](http://clojurians.slack.com)
* [Official Google group](https://groups.google.com/forum/#!forum/clojurescript)
* [Cljs js](http://cljsjs.github.io/) - javascript foreigner libraries for ClojureScript


**Books & Tutorials**
* [ClojureScript Unraveled](http://funcool.github.io/clojurescript-unraveled/)
* [Clojure cookbook](https://github.com/clojure-cookbook/clojure-cookbook)
* [Living Clojure]()
* [Lighttable Koans](https://github.com/practicalli/lighttable-koans) - exercises to help you discover Clojure 
* [ClojureBridge curiculum](https://github.com/ClojureBridge/curriculum)
* [Clojure for the brave and the true](http://www.braveclojure.com/) - a Clojure tutorial (using Emacs)
* [Modern Clojurescript](https://github.com/magomimmo/modern-cljs) - 2nd edition moving to boot for build management (wip)
* [Reagent Tutorial](https://github.com/jonase/reagent-tutorial)
* [Reagend Cookbook](https://github.com/reagent-project/reagent-cookbook)


**Misc**
* [ClojureScript REPL with Microsoft Excel](https://www.cljs4excel.com/)
* [London Clojurians dojo: Something fun with ClojureScript](https://github.com/mikeholmesuk/something-fun-cljs)

| Author | Date |
| -- | -- |
|John Stevenson | Sat 23 Jan 2016 13:40:30 BST |
