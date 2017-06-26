# Leiningen Build tool

[Leiningen](http://leiningen.org/) (pronounced line-ing) is the build automation tool used to manage Clojure projects.  Features include:
 
* Creating Clojure Projects
* Dependency Management
* Running browser-REPL interactive environment (figwheel plugin)

<div align="center">
![Leiningen - build automation for Clojure](../images/leiningen-repl-custom-prompt.png)
</div>

## Install Leiningen

   Install Leiningen by saving the Leiningen install script to somewhere on your operating system path, eg `~/bin`and then running that script from the command line.

* [Install script for Linux & MacOSX](https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein)
* [Install script for Microsoft Windows](https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein.bat)


On Linux and MacOSX, make the script executable first and then run the `lein` script

```bash
chmod a+x ~/bin/lein
lein
```

> **hint** I create a `~/bin` directory and add it to my operating system execution path ($PATH), placing the `lein` script in `~/bin` so I can call it from anywhere on the filesystem.


The first time you run this script it downloads a Java archive file (JAR) of the latest version of Leiningen.  When you run the script again, you have a working Leiningen build tool.

## Testing Leiningen

  Test that Leiningen is installed with the following command

    lein version

  Output should look similar to:

    Leiningen 2.7.1 on Java 1.8.0 Java HotSpot(TM) 64-Bit Server VM
