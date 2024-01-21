# Contributing to Practicalli

Practicalli books are written in markdown and use MkDocs to generate the published website via a GitHub workflow.  MkDocs can also run a local server using the `make docs` target from the `Makefile`

By submitting content ideas and corrections you are agreeing they can be used in this book under the [Creative Commons Attribution ShareAlike 4.0 International license](https://creativecommons.org/licenses/by-sa/4.0/){target=_blank}.  Attribution will be detailed via [GitHub contributors](https://github.com/practicalli/clojurescript/graphs/contributors){target=_blank}.

All content and interaction with any persons or systems must be done so with respect and within the Practicalli Code of Conduct.

## Book status

[![MegaLinter](https://github.com/practicalli/clojurescript/actions/workflows/megalinter.yaml/badge.svg)](https://github.com/practicalli/clojurescript/actions/workflows/megalinter.yaml){target=_blank}
[![Publish Book](https://github.com/practicalli/clojurescript/actions/workflows/publish-book.yaml/badge.svg)](https://github.com/practicalli/clojurescript/actions/workflows/publish-book.yaml){target=_blank}
[![pages-build-deployment](https://github.com/practicalli/clojurescript/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/practicalli/clojurescript/actions/workflows/pages/pages-build-deployment){target=_blank}

[![Ideas & issues](https://img.shields.io/github/issues/practicalli/clojure?label=content%20ideas&logo=github)](https://img.shields.io/github/issues/practicalli/clojure?label=content%20ideas&logo=github){target=_blank}
[![GitHub pull requests](https://img.shields.io/github/issues-pr-raw/practicalli/clojure?label=pull%20requests&logo=github)](https://img.shields.io/github/issues-pr-raw/practicalli/clojure?label=pull%20requests&logo=github){target=_blank}

[![GitHub commit activity](https://img.shields.io/github/commit-activity/y/practicalli/clojure?label=commits&logo=github)](https://img.shields.io/github/commit-activity/y/practicalli/clojure?label=commits&logo=github){target=_blank}
![GitHub contributors](https://img.shields.io/github/contributors/practicalli/clojure?style=for-the-badge&label=github%20contributors)

## Submit and issue or idea

If something doesnt seem quite right or something is missing from the book, please [raise an issue via the GitHub repository](https://github.com/practicalli/clojure/issues){target=_blank} explaining in as much detail as you can.

**Raising an issue before creating a pull request will save you and the maintainer time**.

## Considering a Pull request?

!!! INFO "Pull Request Commits must be cryptographically signed"
    All commits contributed to Practicalli must be signed via a legitimate SSH or GPG key to avoid the risk of commit spoofing.

    [Configure commit signing with SSH key - Practicalli Engineering](https://practical.li/engineering-playbook/source-control/git-configuration/#commit-signing-with-ssh-key){target=_blank .md-button}

All pull requests must include an entry in CHANGELOG.md or will not be merged.  A changelog entry allows the community to follow the changes to the book.

Each pull request will have a number of CI workflows run against the contribution, checking the format of the content and if a changelog entry has been provided.

Please keep pull requests small and focused, as they are much quicker to review and easier to accept.  Ideally PR's should be for a specific page or at most a section.

A PR with a list of changes across different sections will be closed without merging as these take considerable time to review.

Issues such as grammar improvements are typically a sign of a rushed section that requires a rewrite, so a pull request to fix a typeographic error will probably not be merged.  Raise an issue, or post a thread in the [:globe_with_meridians: Clojurians Slack #practicall channel](https://clojurians.slack.com/messages/practicalli)

## Thank you to everyone that has contributed

A huge thank you to Rich Hickey and the team at Cognitect for creating and continually guiding the Clojure language.  Special thank you to Alex Miller who has provided excellent advice on working with Clojure and the CLI tooling.

The Clojure community has been highly supportive of everyone using Clojure and I'd like to thank everyone for the feedback and contributions.  I would also like to thank everyone that has joined in with the [London Clojurins community](https://www.meetup.com/London-Clojurians/){target=_blank}, [ClojureBridgeLondon](https://clojurebridgelondon.github.io/){target=_blank}, [Clojurians Slack community](http://clojurians.net/){target=_blank}, [Clojurians Zulip](https://clojurians.zulipchat.com/){target=_blank} community and [Clojureverse community](https://clojureverse.org/){target=_blank}.

Thank you to everyone who sponsors the Practicalli websites and videos and for the [Clojurists Together sponsorship](https://www.clojuriststogether.org/){target=_blank}, it helps me continue the work at a much faster pace.

Special thanks to [Bruce Durling](https://twitter.com/otfrom){target=_blank} for getting me into Cloure in the first place.

![GitHub contributors](https://img.shields.io/github/contributors/practicalli/clojure?style=for-the-badge&label=github%20contributors)
