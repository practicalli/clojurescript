# Continuous testing during development

Running a figwheel-main build includes continuous testing service, so you can instantly see the results of your tests once the application has started.

```shell
clojure -M:fig:build
```

[http://localhost:9500/figwheel-extra-main/auto-testing](http://localhost:9500/figwheel-extra-main/auto-testing) will show the live results of running the tests.

![Figwheel-main - tests - auto-testing webpage results](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojurescript/figwheel/figwheel-main-tests-auto-testing-webpage.png)


You may see the auto-testing host page display before showing the test results, or if the web page is reloaded (or if your tests take a long time to run or there are no tests to run)

![Figwheel-main - tests - auto-testng host page](https://raw.githubusercontent.com/practicalli/graphic-design/live/clojurescript/figwheel/figwheel-main-tests-auto-testing-host-page.png)
