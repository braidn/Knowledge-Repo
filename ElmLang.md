# Elm

* Compiled language that kinda looks like coffeescript.
* Highly functional, taking a lot of tenants from Haskell.
* Due to the compilation, a `Main.elm` and an `Main` function as 
an entry point is pretty common.

## Conventions

* Namespacing imports seems like a good way of building an app.
  * This can be done during the module exports phase:
  * ex: `module SomeComponent.ComponentName exposing (some_func)`

## General Syntax

* `module` statement acts like a module exports in es6
* `import` used to import modules and expose functions to the script.