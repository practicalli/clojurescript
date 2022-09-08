# Summary

* [Introduction](introduction.md)

## Getting Started

* [Install](install/index.md)
* [Browser DevTools](install/browser-devtools.md)
    <!-- * [Java](install/java.md) -->
    <!-- * [Leiningen](install/leiningen.md) -->
    <!-- * [Figwheel](install/figwheel.md) -->
    <!-- * [Chestnut](install/chestnut.md) -->
    <!-- * [CIDER](install/cider.md) -->

## Figwheel-main

* [Figwheel projects](figwheel-main-projects/index.md)
    * [Simple project](figwheel-main-projects/simple.md)
    * [Reagent project](figwheel-main-projects/reagent.md)

* [Figwheel Workflow](figwheel-main/index.md)
    * [Create Projects](figwheel-main/create-project.md)
    * [Project Configuration](figwheel-main/project-configuration.md)
    * [Run Figwheel](figwheel-main/check-configuration.md)
    * [Rebel Rich UI](figwheel-main/rebel.md)
    * [Build project](figwheel-main/build-project.md)
    * [Emacs Cider](figwheel-main/run-figwheel-from-cider.md)
    * [Run tests](figwheel-main/run-tests.md)
    * [Continuous Tests](figwheel-main/continuous-testing.md)
    * [Package project](figwheel-main/package-project.md)
    * [Pages deploy](figwheel-main/pages-deploy.md)

## HTML Content

* [Hiccup syntax](hiccup-style-syntax.md)

<!-- * [Selma](selma.md) -->

## Styling Web pages

* [Bulma CSS](css/bulma.md)
<!-- * [Bootstrap](css/bootstrap.md) -->
<!-- * [Tailwind](css/tailwind.md) -->

<!-- ## Deployment -->

<!-- * [Deploy ClojureScript](deploy/index.md) -->
<!--     * [GitHub Pages](deploy/github-pages.md) -->
<!--     * [GitLab Pages](deploy/gitlab-pages.md) -->

## Reagent Projects

* [Reagent Overview](reagent/index.md)
* [ClojureBridge website](web-design-basics/clojurebridge-london-website/index.md)
    * [Create project](web-design-basics/clojurebridge-london-website/create-project.md)
    * [Add Bulma CSS](web-design-basics/clojurebridge-london-website/add-bluma-css.md)
    * [Run the project](web-design-basics/clojurebridge-london-website/run-the-project.md)
    * [Live reloading](web-design-basics/clojurebridge-london-website/live-reloading.md)
    * [Hiccup for HTML](web-design-basics/clojurebridge-london-website/hiccup-for-html.md)
    * [REPL workflow](web-design-basics/clojurebridge-london-website/repl-workflow.md)
    * [Organising the code](web-design-basics/clojurebridge-london-website/organising-the-code.md)
    * [Add welcome message](web-design-basics/clojurebridge-london-website/add-welcome-message.md)
    * [Add welcome section](web-design-basics/clojurebridge-london-website/add-welcome-section.md)
    * [Responsive design](web-design-basics/clojurebridge-london-website/responsive-design.md)
    * [App State section](web-design-basics/clojurebridge-london-website/app-state-section.md)
    * [GitHub pages deploy](web-design-basics/clojurebridge-london-website/github-pages-deploy.md)
    * [Deploy build](web-design-basics/clojurebridge-london-website/deploy-build.md)
    * [Add Content namespace](web-design-basics/clojurebridge-london-website/add-content-namespace.md)
    * [Add more sections](web-design-basics/clojurebridge-london-website/add-more-sections.md)
    * [Navigation bar](web-design-basics/clojurebridge-london-website/add-navigation.md)
    * [Interacting](web-design-basics/clojurebridge-london-website/interacting/index.md)

* [tic-tac-toe game](reagent-projects/tic-tac-toe/index.md)
    * [Create Project](reagent-projects/tic-tac-toe/create-project.md)
        * [Add Project to Git](reagent-projects/tic-tac-toe/add-project-to-git.md)
    * [Start the REPL with Figwheel](reagent-projects/tic-tac-toe/start-the-repl.md)
        * [Test Figwheel](reagent-projects/tic-tac-toe/test-figwheel.md)
    * [Chrome DevTools](reagent-projects/tic-tac-toe/chrome-devtools.md)
        * [Cljs DevTools addon](reagent-projects/tic-tac-toe/cljs-devtools-addon.md)
    * [Review reagent Project](reagent-projects/tic-tac-toe/review-reagent-project.md)
        * [Figwheel Helper functions](reagent-projects/tic-tac-toe/figwheel-helper-functions.md)
    * [Interact with the REPL](reagent-projects/tic-tac-toe/interact-with-the-repl.md)
        * [Via the Editor](reagent-projects/tic-tac-toe/interact-with-the-repl-via-editor.md)
        * [Evaluate code in REPL](reagent-projects/tic-tac-toe/interact-with-the-repl-evaluate-code.md)
        * [REPL in dev console](reagent-projects/tic-tac-toe/repl-in-developer-console.md)
    * [Reagent Design](reagent-projects/tic-tac-toe/reagent-design.md)
        * [Defining Components](reagent-projects/tic-tac-toe/reagent-design-defining-components.md)
        * [Manage app-state](reagent-projects/tic-tac-toe/reagent-design-manage-app-state.md)
        * [Reloading State](reagent-projects/tic-tac-toe/reagent-design-reloading-state.md)
    * [Component: tictactoe-game](reagent-projects/tic-tac-toe/component-tictactoe-game.md)
    * [Design Game board](reagent-projects/tic-tac-toe/design-game-board.md)
    * [Component: Game board](reagent-projects/tic-tac-toe/component-game-board.md)
        * [Hiccup style syntax](reagent-projects/tic-tac-toe/hiccup-style-syntax.md)
        * [Scalable Vector Graphics](reagent-projects/tic-tac-toe/svg-overview.md)
        * [React unique index](reagent-projects/tic-tac-toe/react-unique-index.md)
    * [Render Game Board](reagent-projects/tic-tac-toe/render-game-board.md)
    * [Update Game Board](reagent-projects/tic-tac-toe/update-game-board.md)
    * [Refactor into components](reagent-projects/tic-tac-toe/refactor-into-components.md)
        * [Empty Cell](reagent-projects/tic-tac-toe/refactor--empty-cell.md)
        * [Nought Cell](reagent-projects/tic-tac-toe/refactor--nought-cell.md)
        * [Cross Cell](reagent-projects/tic-tac-toe/refactor--cross-cell.md)
    * [Button: Start a new game](reagent-projects/tic-tac-toe/button--start-a-new-game.md)
    * [Computer moves](reagent-projects/tic-tac-toe/computer-moves.md)
        * [Basic move](reagent-projects/tic-tac-toe/computer-move--basic.md)
        * [REPL experiments](reagent-projects/tic-tac-toe/computer-move--repl-experiments.md)
        * [Random available cell](reagent-projects/tic-tac-toe/computer-move--random-available-cell.md)
    * [Detecting Victory](reagent-projects/tic-tac-toe/detecting-victory.md)
        * [Experiments in the REPL](reagent-projects/tic-tac-toe/detecting-victory-repl-experiments.md)
        * [Experiments in the REPL - Pattern matching](reagent-projects/tic-tac-toe/detecting-victory-repl-experiments-pattern-matching.md)
        * [Victory function](reagent-projects/tic-tac-toe/detecting-victory-function.md)


<!-- ## Full Stack projects -->
<!-- ## Isomorphic projects -->
<!-- ClojureScript on backend and frontend -->

## Reference

* [ClojureScript Overview](overview/index.md)
    * [Single Page Apps](overview/single-page-apps.md)
    * [Compiling to JavaScript](overview/compiling-to-javascript.md)
    * [ClojureScript platforms](overview/clojurescript-platforms.md)
    * [Functional Programming](overview/functional-programming.md)
    * [Reactive apps](overview/reactive-apps.md)
        * [Facebook React](overview/react-facebook.md)
        * [Om and Om Next](overview/react-om-and-om-next.md)
        * [Reagent](overview/react-reagent.md)
        * [Re-frame](overview/react-re-frame.md)
        * [React Native](why-clojurescript/react-native.md)

* [Why ClojureScript](why-clojurescript/index.md)
    * [Lightweight](why-clojurescript/lightweight.md)
    * [Google Closure](why-clojurescript/google-clojure.md)
    * [Source Maps](why-clojurescript/source-maps.md)
    * [Interoperability](why-clojurescript/interoperability.md)
    * [Why not JavaScript](why-clojurescript/why-not-javascript.md)
    * [Who uses ClojureScript](why-clojurescript/who-uses-clojurescript.md)

* [Web Design basics](web-design-basics/index.md)
    * [Bootstrap](web-design-basics/bootstrap.md)
        <!-- * [Container](web-design-basics/bootstrap-container.md) -->
        * [Jumbotron](web-design-basics/bootstrap-jumbotron.md)
    * [Bootstrap website](web-design-basics/clojurebridge-london-bootstrap-website.md)


<!-- ## TODO -->

<!-- * [cloud data stores](cloud-datastores/index.md) -->
<!--     * [Firebase](cloud-datastores/firebase/index.md) -->
<!--     * [Heroku Postgres](cloud-datastores/heroku-postgres/index.md) -->
<!--     * [Heroku Redis](cloud-datastores/heroku-postgres/index.md) -->
<!--     * [Amazon AWS](cloud-datastores/amazon-aws/index.md) -->


## Old Material - under review

* [Clojurescript Quickstart](quickstart/index.md)
    * [Create basic project](quickstart/create-basic-project.md)
    * [Hello World](quickstart/hello-world.md)
    * [Create build file](quickstart/create-build-file.md)
    * [Build Project](quickstart/build-project.md)
    * [Create a web page](quickstart/create-a-web-page.md)
    * [Google Closure](quickstart/google-clojure.md)
    * [Reduce boilerplate](quickstart/reduce-boilerplate.md)
    * [Auto-building](quickstart/auto-building.md)
    * [Browser REPL](quickstart/browser-repl.md)
    * [Production Build](quickstart/production-build.md)
    * [Dependencies](quickstart/dependencies.md)
    * [node.js](quickstart/nodejs.md)
    * [Lumo](quickstart/lumo.md)
        * [Self Hosted Clojurescript](quickstart/self-hosted-clojurescript.md)

* [Figwheel Classic](figwheel/index.md)
    * [Features](figwheel/features.md)
    * [Flappy Birds demo](figwheel/flappy-birds-demo.md)
    * [Using Figwheel](figwheel/using-figwheel.md)
    * [Configure Build ](figwheel/configure-build.md)
    * [Server-side Config](figwheel/server-side-config.md)
    * [Client-side use](figwheel/client-side-use.md)
    * [Client-side Config](figwheel/client-side-config.md)
    * [File Reloads](figwheel/file-reloads.md)
    * [REPL Control](figwheel/repl-control.md)
    * [Editor REPLs & nREPL](figwheel/editor-repls-nrepl.md)
    * [Scripting Figwheel](figwheel/scripting-figwheel.md)
    * [Scripting with Component](figwheel/scripting-with-component.md)
    * [Re-loadable Code](figwheel/re-loadable-code.md)

* [Figwheel Classic Project](figwheel-project/index.md)
    * [Create Project](figwheel-project/create-project.md)
    * [ClojureScript file](figwheel-project/clojurescript-file.md)
    * [Project Build file](figwheel-project/project-build-file.md)
    * [Run Figwheel](figwheel-project/run-figwheel.md)
    * [Web Page](figwheel-project/web-page.md)
    * [Run Figwheel again](figwheel-project/run-figwheel-again.md)
    * [Add a counter](figwheel-project/add-a-counter.md)
    * [Auto Reloading](figwheel-project/auto-reloading.md)
    * [Serving assets](figwheel-project/serving-assets.md)
    * [Using the REPL](figwheel-project/using-the-repl.md)

* [Clojurescript Examples](clojurescript-examples/index.md)
    * [JavaScript Alerts](clojurescript-examples/javascript-alerts.md)
    * [Writing to the JavaScript console](clojurescript-examples/writing-to-javascript-console.md)
    * [Buttons](clojurescript-examples/buttons.md)
    * [Forms](clojurescript-examples/forms.md)

* [Functional Reactive Programming](functional-reactive-programming/index.md)
    * [react.js](reactjs/index.md)
        * [Project: Calculator](reactjs/project-calculator-introduction.md)
            * [Create Project](reactjs/project-calculator-create-project.md)
    * [Reagent](reagent/index.md)
    * [Reagent Project: ClojureX](reagent-project-clojurex/index.md)
        * [Create Project](reagent-project-clojurex/create-project.md)
        * [Start the REPL](reagent-project-clojurex/start-the-repl.md)
        * [Project so far](reagent-project-clojurex/project-so-far.md)
        * [Interact with the REPL](reagent-project-clojurex/interact-with-the-repl.md)
        * [Create Conference Title](reagent-project-clojurex/index.md)(om-project-clojurex/create-conference-title.md)
        * [Designing Session Model](reagent-project-clojurex/index.md)(om-project-clojurex/designing-session-model.md)
        * [Display Session in root-component](reagent-project-clojurex/index.md)(om-project-clojurex/display-session-in-root-component.md)
        * [Refactor to Multi-Session Model](reagent-project-clojurex/refactor-to-multi-session-model.md)
        * [Refactor root-component for sessions](reagent-project-clojurex/index.md)
        * [Defining new session data](reagent-project-clojurex/index.md)
        * [Adding session data to State](reagent-project-clojurex/index.md)
        * [Include Bootstrap](reagent-project-clojurex/index.md)
        * [Add a Container](reagent-project-clojurex/index.md)
        * [Add Header Style](reagent-project-clojurex/index.md)
        * [Add Session Style](reagent-project-clojurex/index.md)
        * [Create Sessions Component](reagent-project-clojurex/index.md)
        * [Add Session Form](reagent-project-clojurex/index.md)

    <!-- * [Re-frame](re-frame/index.md) -->
    <!--     * [Re-frame ToDo MVC](re-frame/todo-mvc.md) -->

    * [Om](om/index.md)
        * [Overview](om/overview.md)
    * [Om Project: ClojureX](om-project-clojurex/index.md)
        * [Create Project](om-project-clojurex/create-project.md)
        * [Start the REPL](om-project-clojurex/start-the-repl.md)
        * [Interact with Project](om-project-clojurex/interact-with-project.md)
        * [Create Conference Title](om-project-clojurex/create-conference-title.md)
        * [Designing Session Model](om-project-clojurex/designing-session-model.md)
        * [Display Session in root-component](om-project-clojurex/display-session-in-root-component.md)
        * [Refactor to Multi-Session Model](om-project-clojurex/refactor-to-multi-session-model.md)
        * [Refactor root-component for sessions](om-project-clojurex/refactor-root-component-for-sessions.md)
        * [Defining new session data](om-project-clojurex/defining-session-data.md)
        * [Adding session data to State](om-project-clojurex/adding-session-data-to-state.md)
        * [Include Bootstrap](om-project-clojurex/include-bootstrap.md)
        * [Add a Container](om-project-clojurex/add-a-container.md)
        * [Add Header Style](om-project-clojurex/add-header-style.md)
        * [Add Session Style](om-project-clojurex/add-session-style.md)
        * [Create Sessions Component](om-project-clojurex/create-sessions-component.md)
        * [Add Session Form](om-project-clojurex/add-session-form.md)
        * [Om Cursors](om-project-clojurex/om-cursors.md)
        * [Form Click Handler](om-project-clojurex/form-click-handler.md)
        * [Create local State for form](om-project-clojurex/create-local-state-for-form.md)
        * [Use local state in session form](om-project-clojurex/use-local-state-in-session-form.md)
        * [Connect form to local state](om-project-clojurex/connect-form-to-local-state.md)
        * [Add Cursor to Local State](om-project-clojurex/add-cursor-to-local-state.md)
        * [Create Form Component](om-project-clojurex/create-form-component.md)
        * [Testing](om-project-clojurex/testing.md)
    * [Reference](reference/index.md)
        * [Namespaces](create-a-project/namespaces.md)
        <!-- * [Related Libraries](related-libraries/index.md) -->
        <!-- * [Testing](testing/index.md) -->
        * [Clojure Syntax](clojure-syntax/index.md)
            * [Basic Syntax](clojure-syntax/basic-syntax.md)
            * [Clojure data types](clojure-syntax/data-types.md)
            * [Strings](clojure-syntax/strings.md)
            * [Maths](clojure-syntax/maths.md)
            * [Naming & Binding](clojure-syntax/naming-binding.md)
            * [Functions](clojure-syntax/functions.md)
            * [Persistent Data Structures](clojure-syntax/persistent-data-structures.md)
                * [Lists](clojure-syntax/persistent-data-structures-lists.md)
                * [Maps](clojure-syntax/persistent-data-structures-maps.md)
                * [Vectors](clojure-syntax/persistent-data-structures-vectors.md)
                * [Sets](clojure-syntax/persistent-data-structures-sets.md)
            * [Destructuring](clojure-syntax/destructuring.md)
            * [Control flow](clojure-syntax/control-flow.md)
            * [Local Assignment](clojure-syntax/local-assignement.md)
        * [Production](production/index.md)
            * [Externs](production/externs.md)
