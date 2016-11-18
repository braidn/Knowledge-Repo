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

## Lists

* `++` concats two lists together. Each side of the operator must be a list though
  * this can be expensive because it has to walk the entire length of the prepending list.
* `::` is a cons operator and will therefore add the item to the left of the op to the list on the right.
* There are some handy methods built into `List`:
  * `List.head list` returns the first element of the list
  * `List.tail list` returns all but the first element of the list (opposite of above).
  * `List.maximum list` finds the largest 'element' in the list (SUPER handy)
  * `List.member item list` returns true or false if the item is in the list (equally handy)
* Lists, like in Ruby, can be built using range operators `[1..22]` with returns the sequential list

### Tuples

* A type of list but instead of being surrounded by square brackets, surrounded with parens.
  * ex: `([1,2], [2,3], [4,5])`
* Unlike a list, tuples can contain multiple different types.
* Each element must have the same amount of data.
  * This is really when you want to use a tuple, when you know the _exact_ structure of your data.

## Types

* Elm runs with type inference so no need to tell the compiler that an obvious Int is an Int

[1]: https://wiki.haskell.org/Infix_operator