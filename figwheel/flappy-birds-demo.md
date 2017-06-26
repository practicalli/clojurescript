# Figwheel Demo

> **TODO** Discover the basic concept of Figwheel by experimenting with the flappy birds demo project

![Figwheel Flappy Birds](https://camo.githubusercontent.com/b667870d8c1820794e361866908ae7930acb9c77/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f626861756d616e2d626c6f672d696d616765732f666967776865656c5f696d6167652e706e67)

Clone the flappy bird demo from Github:

    git clone https://github.com/bhauman/flappy-bird-demo.git

Change into the `flappy-bird-demo` directory on the command line and run:

    lein figwheel

In your browser, open `http://localhost:3449/index.html` and once flappy birds has loaded, open your browsers development tools / console 

In your editor, open `src/flappy_bird_demo/core.cljs` and make changes to the code.

As soon as you save your code you see the changes in the browser window.  You will also see the ClojureScript logo briefly display in the browser window, to indicate that the new changes have been added

![Image of browser window with Cljs logo signifying a change is being made]()

Make sure you open your browser's development console so you can get feedback about code reloads.

> **Hint** Place your browser window and code editor window side by side so you can see the changes as you save them.  The changes should apply instantly.


## Suggested changes

Try and change some of the following aspects of the game

  - the Start and Restart button names
  - remove the start button
  - the size and speed of the birds bounce (based on a sine wave)
  - the jump velocity of the bird
  - turn off collision detection
  - stop the rendering of the pillars
  - the gap between the pillars

Some suggested changes have been added to a [Github Gist of the ClojureScript code](https://gist.github.com/jr0cket/166a9ef7e717e9c348c9).
