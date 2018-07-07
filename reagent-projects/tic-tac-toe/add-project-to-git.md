# Tic-tac-toe: Add Project to Git Version Control

To manages the changes in the project I am using Git version control.

The [figwheel template]() includes a `.gitignore` file that defines file & directories that should automatically be excluded from any commit.

> ####Note::Create local git repository and commit changes
>
```bash
git init
git add .
git commit -m "Leiningen Project using figwheel template with reagent option"
```

This initial commit should have included the following files:

[![Git initial project commit](/images/clojurescript-project-reagent-tictactoe--git-initial-commit.png)](/images/clojurescript-project-reagent-tictactoe--git-initial-commit.png)



## Optionally: Update project description & license

I encourage you to write a simple project description in the `project.clj` file to give a high level idea of what the project is about.

If the project is open source then I also include the online repository for the code in the `:url` section.

I also prefer to use a Creative Commons license rather than the Eclipse public license for open source works.

[![Project description & license updates](/images/clojurescript-project-reagent-tictactoe--project-description-and-license-updated.png)](/images/clojurescript-project-reagent-tictactoe--project-description-and-license-updated.png)


## Reference: Default exclusions in .gitignore

The figwheel template includes a `.gitignore` file including the relevant patterns to exclude files that are typically not useful to commit to a git repository.

```text
/resources/public/js/compiled/**
figwheel_server.log
pom.xml
*jar
/lib/
/classes/
/out/
/target/
.lein-deps-sum
.lein-repl-history
.lein-plugins/
.repl
.nrepl-port
```

> ####Hint::Avoid including tooling & editor specific exclusions
> The `.gitignore` file should only be used for project specific exclusions.
>
> If you have common exclusions for your tooling or editors across multiple projects, then you can use the `~/.gitignore_global` file.
>
> [Git Ignore for Clojure & Emacs - ignore Emacs backup & temporary files](http://jr0cket.co.uk/2012/12/gitignore-for-clojure-and-emacs.html.html)
