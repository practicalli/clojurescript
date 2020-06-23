# Interacting with the website

> #### TODO::work in progress, sorry

So far our website has been pretty static.  We can change the page by saving new function definitions or by updating data in the application state.

What about user interaction?

In this section we will learn how to interact with the website and understand how reagent manages updates for us.

Ideas we could do

- a daily like / love / interested button  - each time the button is pressed it increases the number of likes (eg. a fancy counter).  Without persisting the number of likes in a data store, the number of likes would be reset each time the application is deployed.

- minimise a section, minimise all sections but that which you click on
