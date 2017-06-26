# Create the project

Create the project using the Leiningen Chestnut template

```
lein new chestnut conference-reagent -- --reagent
```

This will create a new project that includes the Reagent libraries (rather than the default om libraries).

> #### Hint::Passing Options to Leiningen
> The `--` after the project name is needed to tell the command line to pass the option `--reagent` to the `lein` command, rather than be interpreted by the command line shell itself.

Open the `conference-reagent/project.clj` file to review the dependencies already added to the project.

The only difference in dependencies is `[reagent "0.6.0-rc"]` instead of `omcljs/om`.

```clj
  :dependencies [[org.clojure/clojure "1.8.0"]
                 [org.clojure/clojurescript "1.9.89" :scope "provided"]
                 [com.cognitect/transit-clj "0.8.285"]
                 [ring "1.4.0"]
                 [ring/ring-defaults "0.2.0"]
                 [bk/ring-gzip "0.1.1"]
                 [ring.middleware.logger "0.5.0"]
                 [compojure "1.5.0"]
                 [environ "1.0.3"]
                 [reagent "0.6.0-rc"]]
```

> #### Hint::Running multiple projects

> To use Figwheel with multiple projects we will need to change the `:server-port` configuration to use a different port number.

> Edit the `project.clj`.

> Find the `:figwheel` section.

> Uncomment the `:server-port` configuration and change the number to something unique, eg. 3450

