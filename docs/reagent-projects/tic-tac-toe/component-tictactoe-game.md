# Component: TicTacToe

A reagent component is simply a Clojure function.  So we can take the hello world function and change it to `tictactoe-game`.

First we will add a simple title and message to the component.  So the text of these is not hard-coded in the component, we will pull them from the app-state.

```clojure
(defn tictactoe-game []
  [:div
   [:h1 (get-in @app-state [:page :title])]
   [:p  (get-in @app-state [:page :message])]])
```


Now lets update the `app-state` to hold the title and message we want to display in the component.


```clojure
(defonce app-state
           (atom
             {:page
               {:title "Lets Play TicTacToe"
                :message "Do you want to play a game?"}}))
```


Next we need to model the game board and add the board to the `tictactoe-game` component.
