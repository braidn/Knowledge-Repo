# Elm

* Compiled language that kinda looks like coffeescript.
* Highly functional, taking a lot of tenants from Haskell.
* Due to the compilation, a `Main.elm` and an `Main` function as 
an entry point is pretty common.
* One of the largest differences from Elm to Haskell is Elm is eager where Haskell is lazy

## Conventions

* Namespacing imports seems like a good way of building an app.
  * This can be done during the module exports phase:
  * ex: `module SomeComponent.ComponentName exposing (some_func)`
* Overall architecture often follows the following conventions:
  * An initial model, an initializer, a view function, an update function, and a subscriptions function.
  * An easier way of thinking about this: model, update, view.
* Messages can pass from one module to another much like an event bus pattern.

## General Syntax

* `module` statement acts like a module exports in es6
* `import` used to import modules and expose functions to the script.
* Backticks(`) can be used to force a function to be [infix][1]
* Like many Lisp like languages, function application is performed with spaces, not parens.
  * `bar 5 1` versus `bar(5, 1)`

[1]: https://wiki.haskell.org/Infix_operator