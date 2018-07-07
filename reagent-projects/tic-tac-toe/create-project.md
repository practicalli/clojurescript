# Tic-tac-toe: Create project

> ####Note::Create a project called tictactoe-reagent
> Use Leiningen build tool to create a new Clojurescript project, using the figwheel project template.
```clojure
lein new figwheel tictactoe-reagent -- --reagent
```

[![Create project with leiningen: tic-tac-toe-reagent](/images/clojurescript-project-reagent-tictactoe--create-project-with-figwheel-template.png)](/images/clojurescript-project-reagent-tictactoe--create-project-with-figwheel-template.png)


## Project structure

The project created should have the following files and directories

[![Project structure for tic-tac-toe-reagent](/images/clojurescript-project-reagent-tictactoe--new-project-tree-structure.png)](/images/clojurescript-project-reagent-tictactoe--new-project-tree-structure.png)

You can use any command line or graphical file browser to view the project structure.


## Figwheel template & options

The [`figwheel` template](https://github.com/bhauman/figwheel-template) for Leiningen creates a basic Clojurescript project driven by Figwheel.

The figwheel template takes several options, `--reagent`, `--rum` and `--om`, each of which creates a basic project with the respective libraries.

The `--` between the project name and `--reagent` option ensures this option is passed to the template, rather than being passed to Leiningen itself.
