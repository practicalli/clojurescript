# Creating a Deploy build configuration

Create a build configuration for deployment, to remove the need to copy the `.js` file to the deploy location.

These instructions assume the `/docs` directory is used by GitHub pages for deploying the website.

## Create a deploy build configuration file

Copy the `dev.cljs.edn` to `deploy.cljs.edn`.

Edit `deploy.cljs.edn` and add the `ouptput-to:` configuration option

```clojure
^{:watch-dirs   ["test" "src"]
  :css-dirs     ["resources/public/css"]
  :auto-testing true}
{:main clojurebridge-landing-page.core
 :output-to "docs/cljs-out/dev-main.js"}
```

> #### Hint::Adjust file and path if required
> This configuration assumes GitHub pages has been configured to use the `/docs` directory in the master branch to serve the website.


## Create a new alias

Edit the `project.clj` file.

Add a new `:aliases` line, the same as the `fig:min` line, except using `deploy` at the end.

```clojure
  :aliases {"fig"        ["trampoline" "run" "-m" "figwheel.main"]
            "fig:build"  ["trampoline" "run" "-m" "figwheel.main" "-b" "dev" "-r"]
            "fig:min"    ["run" "-m" "figwheel.main" "-O" "advanced" "-bo" "dev"]
            "fig:deploy" ["run" "-m" "figwheel.main" "-O" "advanced" "-bo" "deploy"]
            "fig:test"   ["run" "-m" "figwheel.main" "-co" "test.cljs.edn" "-m" juxt-edge.test-runner]}
```

## Deploying updates

`lein fig:deploy` will now deploy any changes to your ClojureScript app without the need to copy any files.

In a terminal window open in the root of your project, run the commands:

```shell
lein clean
lein fig:deploy
```

Then commit the new file and push to GitHub

```shell
git commit -a "Deploy version 4.2"
git push origin master
```

If you make any changes to the index.html or css/styles.css files, then still need to copy them into `/docs` directory manually, then commit those changes too.
