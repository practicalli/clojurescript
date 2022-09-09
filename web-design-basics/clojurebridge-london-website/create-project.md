# Create a ClojureScript project

Create a new ClojureScript project for the development of a website for ClojureBridge London

Use the figwheel-main template with the reagent library to create the the foundation of the project code.

{% tabs deps="deps.edn projects", lein="Leiningnen projects" %}

{% content "deps" %}

[Clojure CLI tools](https://practical.li/clojure/clojure-cli/) and [clj-new](https://github.com/seancorfield/clj-new), for example using the `:project/new` alias from [practicalli/clojure-deps-edn](https://practical.li/clojure/clojure-cli/install/community-tools.html) user-level aliases for community tools.
```shell
clj -M:project/new figwheel-main clojurebridge/landing-page -- --reagent
```


{% content "lein" %}

Using [Leiningen](https://github.com/technomancy/leiningen)

```shell
lein new figwheel-main clojurebridge/landing-page -- --reagent
```

{% endtabs %}


A working project is created and when run will show a very basic web page

> #### Hint::figwheel-main template
> [figwheel-main-template](https://github.com/bhauman/figwheel-main-template) project provides a simple way to create a minimal ClojureScript project, optionally using reagent, rum, or react to create a react-style single page app (SPA)
