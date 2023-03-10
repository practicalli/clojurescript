# Tic-tac-toe: Start the REPL with Figwheel

[Figwheel](https://github.com/bhauman/lein-figwheel) provides the connection between your ClojureScript code and the REPL in your browser.

When you save changes to your code (ClojureScript, HTML or CSS) then figwheel will push those changes into the browser REPL and update the page in the browser.

> ####Note::Run Figwheel
> In your terminal window, run figwheel from the project root directory:
```bash
lein figwheel
```
>
> Alternatively:
> start the repl in your Clojure editor, eg in Spacemacs its `clojurescript-jack-in`

{% youtube %}
https://www.youtube.com/watch?v=7QUz81C0hz0
{% endyoutube %}

## What just happened ?

Dependencies for the project were checked and any missing libraries were downloaded (nothing missing in the video above).

The ClojureScript code in the project is compiled.  Once compiled, a new browser window or tab will automatically open at http://localhost:3449/index.html

When figwheel connects to the browser, a ClojureScript REPL prompt connected to the browser appears in the terminal window.


[![Figwheel: connect to browser repl](/images/clojurescript-project-reagent-tictactoe--cli-repl-connected.png)](/images/clojurescript-project-reagent-tictactoe--cli-repl-connected.png)


Figwheel is now running and will auto compile and send all changes to the browser without the need to manually reload the page in the browser.
