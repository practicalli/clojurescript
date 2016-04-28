# Create a project

  Lets create a project called `todo-list` using Leiningen, the build automation tool for Clojure.  This project will run the simplest possible webserver.
  
  On the command line:
  
```bash
lein new todo-list
```

![Leiningen - new project called todo-list](../images/lein-new-todo-list.png)

<hr />

## Take a look at the project structure

To see how our project is layed out, change into the `todo-list` directory created by this command and see the project structure that has been created.
  
  * `project.clj` - the project definition, written in Clojure 
  * `src` for all the source code
  * `test` for unit test code


Here is an example of what our project looks like using the `tree` command (you could use `ls -R` or a graphical file browser if you wish)
  
![Clojure project structure - webdev](/images/project-todo-list-tree.png)


> **Hint** Look closer at the directory hierachy and you will see something has happend to our `todo-list` name.  Unfortunately Java does not like dashes '-' in directory or file names, so Leiningen changes the directory names to `src/todo_list/co` & `test/todo_list` and the initial test to `src/todo_list/core_test.clj`.

