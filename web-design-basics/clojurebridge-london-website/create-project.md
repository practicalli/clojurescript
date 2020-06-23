# Create a ClojureScript project

> ####Note:: Create a ClojureScript website for ClojureBridge London
>
> Create a project using the figwheel template, adding reagent library.
>
> Using [Leiningen](https://github.com/technomancy/leiningen)
```shell
lein new figwheel-main clojurebridge-landing-page -- --reagent
```
>
> or the [Clojure CLI tools](https://clojure.org/guides/getting_started#_clojure_installer_and_cli_tools) and [clj-new](https://github.com/seancorfield/clj-new)
```shell
clj -A:new figwheel-main clojurebridge-landing-page -- --reagent
```


This will create a project with a working web page (usually described as a single page app).

> #### Hint::figwheel-main template
> [figwheel-main-template](https://github.com/bhauman/figwheel-main-template) project provides a simple way to create a minimal ClojureScript project, optionally using reagent, rum, om or react/sablono
