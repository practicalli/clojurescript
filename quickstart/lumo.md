# Lumo 

[Lumo](https://github.com/anmonteiro/lumo) is a fast, stand-alone Clojurescript REPL that runs on [node.js](https://nodejs.org/) and V8 Javascript platforms.

Thanks to [V8’s custom startup snapshots](http://v8project.blogspot.com/2015/09/custom-startup-snapshots.html), Lumo starts up instantaneously, making it the fastest Clojure REPL in existence.  However, as Lumo runs bootstrapped ClojureScript then compiling ClojureScript in JavaScript is generally slower than on the JVM.

Here is a comparison of Clojure, Planck and Lumo’s startup times.

![Clojure REPL startup time comparison - Java, Plank & Lumo](../images/lumo-clojure-repl-startup-times-comparison.png)

Lumo employs some tricks to be extremely fast, including caching, lazy analysis cache loading and AOT-compiled macros.

Lumo is free for use and its code is under an Open Source Software license (Eclipse public license).


## Why Node.js

Using Node.js as a platform means Lumo can run on all common operating systems (Ubuntu, MacOSX) and Microsoft Windows.

Node.js has the largest and fastest growing package ecosystem today via [npmjs.com](https://www.npmjs.com/).  Seamless interoperability with NPM plays a huge part in extending ClojureScript’s reach even further.

The fastest Clojure REPL in the world
09 Nov 2016

## Why Lumo?

The startup time of the JVM has been a factor in adoption of Clojure, as starting a Clojure REPL feels slow compared to other tools like node.js.  

Planck — through bootstrapped ClojureScript, and owing to the small latency exhibited by JavaScript VMs — managed to improve the time that it takes to bootstrap a Clojure(Script) REPL. Now Lumo aims to make tooling perform even faster.

## Future Features

Lumo is not complete by any means. The initial release has a substantial set of features `lumo -h` or `lumo --help`

Features planned for Lumo include cursor hopping, pretty printing and colored output, as well as idiomatic ClojureScript wrappers for Node’s APIs, such as performing I/O calls, spawning child processes and more.

## References

* [Lumo - the fastest clojure repl in the world](https://anmonteiro.com/2016/11/the-fastest-clojure-repl-in-the-world/)
