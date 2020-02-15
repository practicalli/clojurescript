# CSS
## SVG
### z-index experiements
https://codepen.io/GarySiu/pen/YBqxjL
## Flexbox layout
https://css-tricks.com/snippets/css/a-guide-to-flexbox/
https://flexboxfroggy.com/




# Github
## Github code for the workshop

The code for this workshop is contained in the Github repository [ClojureScript example](https://github.com/practicalli/clojure-webapps-example), the code for each section is in a specific branch.

To get a copy of the repository, use the following git clone command which creates a new directory called clojure-webapps-example that contains the cloned code.

`git clone https://github.com/practicalli/clojurescript-example.git`

Once you have the repository, use `git checkout branch-name` to get the code for each section.  Each branch is a working application with all the features covered in that section

Use `git branch` to show all the branches available, they should match the names of the sections in this workshop.

Enjoy.




## Deploying to Heroku

This assumes you have a
[Heroku account](https://signup.heroku.com/dc), have installed the
[Heroku toolbelt](https://toolbelt.heroku.com/), and have done a
`heroku login` before.

``` sh
git init
git add -A
git commit
heroku create
git push heroku master:master
heroku open
```

## Running with Foreman

Heroku uses [Foreman](http://ddollar.github.io/foreman/) to run your
app, which uses the `Procfile` in your repository to figure out which
server command to run. Heroku also compiles and runs your code with a
Leiningen "production" profile, instead of "dev". To locally simulate
what Heroku does you can do:

``` sh
lein with-profile -dev,+production uberjar && foreman start
```

Now your app is running at
[http://localhost:5000](http://localhost:5000) in production mode.
## License

Copyright © 2016 FIXME

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.

## Chestnut

Created with [Chestnut](http://plexus.github.io/chestnut/) 0.14.0 (66af6f40).
