# Deploy to GitHub pages

GitHub pages is a free service for serving up content in static files, its ideal for websites that do not require their own database or other services (or simply plugs into purely online services and API's).

Create a repository on GitHub for this ClojureScript project

Add that repository as a remote repository to the local Git repository for this project

```shell
git remote add origin <repository URI from GitHub>

```

## Project specific landing pages

There are two approaches when adding a website to a specific project.

* add files to a `gh-pages` branch (classic approach)
* add files to `/docs` directory on the master branch (new approach)

We will use the new approach and deploy our files in `/docs`


### Alternative: Organisation / user Landing pages

For Organisations on GitHub, like ClojureBridgeLondon and Pracitalli, I use two separate Git repositories

* ClojureScript repository - created by Leiningen / figwheel template
* Deployment repository - only contains specific files for deployment


## Creating the files for deployment

During development the build of the ClojureScript application is contained in multiple files, as this makes it easy to do fast updates of just the specific parts of the application.

When we deploy, we generate a single JavaScript file that contains our application.  We also minify the application to make it quick to load into the browser.

> #### Note::
> In the root of your ClojureScript project (where project.clj file is) run the commands:
```shell
lein clean
lein fig:min
```


## Add directory to GitHub

Create the `/docs` and `/docs/cljs-out` directories in the project first.

Add a `README.md` file with a message describing the purpose of the /docs directory.

Commit the `README.md` file and push to your GitHub repository


## Set GitHub pages location

Visit the GitHub repository website and update the Settings to point to `/docs as the source of GitHub pages

Setting > GitHub Pages > Source

**master branch /docs folder**

![ClojureScript websites - Github Pages source](/images/cljs-website--github-pages-source-docs-on-master.png)


## Copy the files

Copy the following files into the `/docs` directory.

```shell
cp resources/public/index.html docs

cp -r resources/public/css docs

cp -r resources/public/images images

cp resources/public/cljs-out/dev-main.js docs/cljs-out/
```


## Commit and push the files

Commit all the changes in the `/docs` directory.

Push the commit to GitHub
`git push origin master`

Visit your live website at https://<your-git-account>.github.io/clojurebridge-landing-page/


## Deploying updates

Any changes to your ClojureScript app that you want to deploy, then you only need to build the single javascrpt file again

```shell
lein clean
lein fig:min
```

Then copy the new javascript file to the `docs/cljs-out` directory

```shell
cp resources/public/cljs-out/dev-main.js docs/cljs-out/
```

Commit the new file and push to GitHub
```shell
git commit -a "New version"
git push origin master
```

If you make any changes to the index.html or css/styles.css files, then you will need to copy them into `/docs` directory and commit those changes too
