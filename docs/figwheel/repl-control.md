# REPL Control


The Figwheel REPL has the following control functions:

```
Figwheel Controls:
 (stop-autobuild)            ;; stops Figwheel autobuilder
 (start-autobuild [id ...])  ;; starts autobuilder focused on optional ids
 (switch-to-build id ...)    ;; switches autobuilder to different build
 (reset-autobuild)           ;; stops, cleans, and starts autobuilder
 (build-once [id ...])       ;; builds source one time
 (clean-builds [id ..])      ;; deletes compiled cljs target files
 (fig-status)                ;; displays current state of system
```

These functions are special functions that poke through the
ClojureScript env into the underlying Clojure process. As such you
can't compose them.

You can think of these functions having an implicit set of build ids
that they operate on.

If you call `(reset-autobuild)` it will stop the figwheel autobuilder,
clean the builds, reload the build configuration from your
`project.clj` and then restart the autobuild process.

If you call `(stop-autobuild)` it will stop the figwheel autobuilder.

If you call `(start-autobuild)` it will start the figwheel autobuilder
with the current implicit build ids.

If you call `(start-autobuild example)` it will start the figwheel
autobuilder on the provided build id `example`. It will also make
`[example]` the implicit set of build ids.

`start-autobuild` and `switch-to-build` are the only functions that
update the build-id set.

`clean-builds` and `build-once` both allow you to do one off builds and
cleans.  They do not alter the implicit build ids.

`fig-status` displays information on the current Figwheel system state,
including whether the autobuilder is running, which build ids are in
focus, and the number of client connections.
