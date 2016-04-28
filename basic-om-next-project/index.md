# Basic Om-Next project

## What is Om

* V in MVC
* Imediate mode rendering
* Components

## Updating the DOM

Om (and react) compares the latest changes to the virtual dom with the previous version of the dom, essentially creating a diff.  This diff is then applied to the DOM in the browser.  This approach avoids having to query the DOM in the browser which is an incredibly slow process.

