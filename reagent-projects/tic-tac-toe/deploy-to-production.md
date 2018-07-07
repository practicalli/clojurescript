## Production builds

To create a production build, run:

```bash
lein do clean, cljsbuild once min
```

Open your browser in `resources/public/index.html`. You will not get live reloading, nor a REPL.


> ####Hint::What does a production build do
> Creating a production build in this way Minifys the resulting JavaScript code, reducing names of vars and function to a minimum number of characters.  This result in a much smaller JavaScript file which takes a little less time to be transmitted.
>
> The production build also carries out Dead Code analysis, where any code that is never called is simply removed from the resulting JavaScript.
>
> Both these actions result in a much faster execution of the JavaScript code, resulting in a better experience in the web browser.
