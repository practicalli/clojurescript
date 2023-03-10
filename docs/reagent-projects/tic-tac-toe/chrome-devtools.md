# Chrome DevTools

The [Chrome Developer Tools](https://developers.google.com/web/tools/chrome-devtools/) (DevTools for short), are a set of web authoring and debugging tools built into Google Chrome. The DevTools provide web developers deep access into the internals of the browser and their web application. Use the DevTools to efficiently track down layout issues, set JavaScript breakpoints, and get insights for code optimization.

As our ClojureScript generates JavaScript, then the Chrome DevTools provide an additional feedback tool for when our code is running in the browser.

Whilst we build the Tic Tac Toe game we will use the [Console Panel](https://developers.google.com/web/tools/chrome-devtools/console/), [Elements Panel](https://developers.google.com/web/tools/chrome-devtools/css/) and [Sources Panel](https://developers.google.com/web/tools/chrome-devtools/javascript).

> #### Note::Open the DevTools Console
> You can open the DevTools  using one of the following ways
>
> * Keyboard shortcut: Press <kbd>Ctrl</kbd>-<kbd>Shift</kbd>-<kbd>i</kbd>
> * Mouse context menu: Right click on the Hello World page and select Inspect from the menu.
> * The Chrome browser menu: Select "More tools" > "Developer tools"
>
> When the DevTools window opens, select the Console tab.


[![DevTools console - message from ClojureScript](/images/clojurescript-project-reagent-tictactoe--devtools-console.png)](/images/clojurescript-project-reagent-tictactoe--devtools-console.png)


> ####Info::
> If you see a warning message saying "some customer formaters were not rendered", this is fixed on the next page when we "Enable custom formatters"
