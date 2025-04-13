```
██████╗ ██████╗  █████╗  ██████╗████████╗██╗ ██████╗ █████╗ ██╗     ██╗     ██╗
██╔══██╗██╔══██╗██╔══██╗██╔════╝╚══██╔══╝██║██╔════╝██╔══██╗██║     ██║     ██║
██████╔╝██████╔╝███████║██║        ██║   ██║██║     ███████║██║     ██║     ██║
██╔═══╝ ██╔══██╗██╔══██║██║        ██║   ██║██║     ██╔══██║██║     ██║     ██║
██║     ██║  ██║██║  ██║╚██████╗   ██║   ██║╚██████╗██║  ██║███████╗███████╗██║
╚═╝     ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝   ╚═╝   ╚═╝ ╚═════╝╚═╝  ╚═╝╚══════╝╚══════╝╚═╝

 ██████╗██╗      ██████╗      ██╗██╗   ██╗██████╗ ███████╗███████╗ ██████╗██████╗ ██╗██████╗ ████████╗
██╔════╝██║     ██╔═══██╗     ██║██║   ██║██╔══██╗██╔════╝██╔════╝██╔════╝██╔══██╗██║██╔══██╗╚══██╔══╝
██║     ██║     ██║   ██║     ██║██║   ██║██████╔╝█████╗  ███████╗██║     ██████╔╝██║██████╔╝   ██║
██║     ██║     ██║   ██║██   ██║██║   ██║██╔══██╗██╔══╝  ╚════██║██║     ██╔══██╗██║██╔═══╝    ██║
╚██████╗███████╗╚██████╔╝╚█████╔╝╚██████╔╝██║  ██║███████╗███████║╚██████╗██║  ██║██║██║        ██║
 ╚═════╝╚══════╝ ╚═════╝  ╚════╝  ╚═════╝ ╚═╝  ╚═╝╚══════╝╚══════╝ ╚═════╝╚═╝  ╚═╝╚═╝╚═╝        ╚═╝
```

## Book status

![GitHub commit activity](https://img.shields.io/github/commit-activity/m/practicalli/clojurescript?style=for-the-badge)
[![Content ideas and other issues](https://img.shields.io/github/issues/practicalli/clojurescript?label=content%20ideas%20and%20issues&logoColor=green&style=for-the-badge)](https://github.com/practicalli/clojurescript/issues)
[![Pull requests](https://img.shields.io/github/issues-pr/practicalli/clojurescript?style=for-the-badge)](https://github.com/practicalli/clojurescript/pulls)
[![MegaLinter](https://github.com/practicalli/clojurescript/actions/workflows/megalinter.yaml/badge.svg)](https://github.com/practicalli/clojurescript/actions/workflows/megalinter.yaml)
[![GitBook publish](https://github.com/practicalli/clojurescript/actions/workflows/publish-website.yaml/badge.svg)](https://github.com/practicalli/clojurescript/actions/workflows/publish-website.yaml)


## Summary

Learn how to develop simple client-side web applications using the ClojureScript programming language, a functional programming language compiled to JavaScript.

ClojureScipt can be used for simple landing pages with CSS frameworks, Single Page Apps following a react.js approach or complex user interfaces with effective state management.

Figwheel-main is a build tool which provides a highly interactive development workflow, providing instant feedback on code changes.  Figwheel also provides a test runner for continuous unit testing during development.

Reagent, a react-style library, is used for single page applications.  Hiccup and Selma are used for managing content.

Clojure CLI provides an array of tools to support development, using project and user `deps.edn` configuration files.


## Creative commons license

<div style="width:95%; margin:auto;">
  <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>
  This work is licensed under a Creative Commons Attribution 4.0 ShareAlike License (including images & stylesheets).
</div>

## Contributing

Issues and pull requests are most welcome although it is the maintainers discression as to if they are applicable.  Please detail issues as much as you can.  Pull requests are simpler to work with when they are specific to a page or at most a section.  The smaller the change the quicker it is to review and merge.

Please read the [detailed Practicalli contributing page](https://practical.li/contributing/) before raising an issue or pull request to avoid disapointment.

* [Current Issues](https://github.com/practicalli/clojurescript/issues)
* [Current pull requests](https://github.com/practicalli/clojurescript/pulls)

By submitting content ideas and corrections you are agreeing they can be used in this workshop under the [Creative Commons Attribution ShareAlike 4.0 International license](https://creativecommons.org/licenses/by-sa/4.0/).  Attribution will be detailed via [GitHub contributors](https://github.com/practicalli/clojurescript/graphs/contributors).


## Sponsor Practicalli

[![Sponsor Practicalli via GitHub](https://raw.githubusercontent.com/practicalli/graphic-design/live/buttons/practicalli-github-sponsors-button.png)](https://github.com/sponsors/practicalli-johnny/)

All sponsorship funds are used to support the continued development of [Practicalli series of books and videos](https://practical.li/), although most work is done at personal cost and time.

Thanks to [Cognitect](https://www.cognitect.com/), [Nubank](https://nubank.com.br/) and a wide range of other [sponsors](https://github.com/sponsors/practicalli-johnny#sponsors) for your continued support


## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=practicalli/clojurescript&type=Date)](https://star-history.com/#practicalli/clojurescript&Date)


## GitHub Actions

The megalinter GitHub actions will run when a pull request is created,checking basic markdown syntax.

A review of the change will be carried out by the Practicalli team and the PR merged if the change is acceptable.

The Publish Book GitHub action will run when PR's are merged into main (or the Practicalli team pushes changes to the default branch).

Publish book workflow installs Material for MkDocs version 9


## Local development

Install mkdocs version 9 using the Python pip package manager

```shell
pip install mkdocs-material=="9.*"
```

Install the plugins used by the Practicalli site using Pip (these are also installed in the GitHub Action workflow)

```shell
pip3 install mkdocs-material mkdocs-callouts mkdocs-glightbox mkdocs-git-revision-date-localized-plugin mkdocs-redirects pillow cairosvg
```

> pillow and cairosvg python packages are required for [Social Cards](https://squidfunk.github.io/mkdocs-material/setup/setting-up-social-cards/)

Fork the GitHub repository and clone that fork to your computer,

```shell
git clone https://github.com/<your-github-account>/<repository>.git
```

Run a local server from the root of the cloned project

```shell
make docs
```

The website will open at <http://localhost:8000>

If making smaller changes, then only rebuild the content that changes, speeding up the local development process

```shell
make docs-changed
```

> NOTE: navigation changes may not be correctly reflected without reloading the page in the web browser or carrying out a full `make docs` build

