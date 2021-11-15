# Lumo - Fast, cross-platform, standalone ClojureScript environment 

Read the [announcement blog post](https://anmonteiro.com/2016/11/the-fastest-clojure-repl-in-the-world/).

## Contents

- [Installation](#installation)
- [Using Lumo](#using-lumo)
- [Building](#building)
- [Copyright & License](#copyright--license)

## Installation

### Via [NPM](https://www.npmjs.com/package/lumo-cljs)

```shell
$ npm install -g lumo-cljs
```

Note: the installed binary will be named `lumo` rather than `lumo-cljs`_

### Via [Homebrew](http://brew.sh/) (macOS)

```shell
$ brew install lumo
```

**Note:** If you want to install a binary built from master, run `brew install --HEAD lumo`
(at your own responsibility).

### Manual

1. Download the [latest release](https://github.com/anmonteiro/lumo/releases/latest).
2. Move it to somewhere in your `$PATH`.

## Using Lumo

Enter `lumo` at the command line to launch it.

Check out `lumo -h` for usage instructions and supported command line options.

## Building

To build Lumo from source:

1. Make sure you have installed [Boot](http://boot-clj.com/) and [Yarn](https://yarnpkg.com/).
2. At the root of the repository, run: `boot release`.
3. The resulting binary can be found in `build/lumo` (or `build\lumo.exe` if you're
on Windows).
