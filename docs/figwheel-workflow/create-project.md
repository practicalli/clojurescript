# Create figwheel projects

[clj-new](https://github.com/seancorfield/clj-new) uses the Leiningen template format and some template developers will include project configuration for Clojure CLI. Each template designer is responsibility as to which project and build tools it supports.

The [figwheel-main template](https://github.com/bhauman/figwheel-main-template) provides an option to create a Leiningen or Clojure CLI project and clj-new will create a Clojure CLI configuration by default.

> Where a template only provides a Leiningen configuration, dependencies listed in `project.clj` should be added to the `:deps` section of `deps.edn`. `dev-dependencies` in `project.clj` should be satisfied by aliases in the project or user-level `deps.edn` configuration.


## ClojureScript project using figwheel

Use the [figwheel-main template](https://github.com/bhauman/figwheel-main-template) to create a ClojureScript project that uses figwheel-main to manage the build.

In a terminal, use the following command:

```shell
clojure -M:project/new figwheel-main practicalli/hello-world -- --reagent
```

> The `:project/new` alias is defined in [practicalli/clojure-deps-edn user-level configuration](https://practical.li/clojure/clojure-cli/install/community-tools.html) and supports `-M`, `-X` and `T` execution flags.
> The `-X` and `-T` flags use a command with key value arguments
>
> `clojure -T:project/new :template figwheel-main :name practicalli/landing-page :args '["+reagent"]'`


The `practicalli/hello-world` defines the main application namespace as `hello-world` and `practicalli` as the domain.

`--` after the name tells clj-new to pass the following text to the template.

`--reagent` is a template option to add reagent React-style library dependencies to the generated project. `--rum` and `--react` are other React-style libraries that could be used instead of `--reagent`
