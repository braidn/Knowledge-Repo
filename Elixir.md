# Elixir

## Notes

* `ex` files are compiled to bytecode
* `exs` files are more for scripting and not compiled. These are usually reserved for tests.
* Assignments with the = operator are considered matches.
  * Elixir attempts, in all ways possible, to make the left side values the same as the right.
* Elixir's pattern matching allows reassignment where Erlang's doesn't.
* All of Elixir's variables are immutable.
  * if data changes, the original reference is copied, not change.
  * when this copying occurs, parts of the original are repointed to the new objects.
* Each part and piece of code runs in many separate processes.
  * each process has it's own heap which vastly accelerates GC threads.
* Due to the functional aspect, data is always transformed, never changed.
* String interpolation in Elixir is the same as in Ruby.

## Iex Prompt

* Wrap a function/item in `h()` for help.

## Lists

* Created much like arrays in most other languages
* The assignment operator can cast a list onto another list.
  * This would assign each of the characters of the second list to each of the first. 

## Value Types

* Integers can contain `_` which is used to separate large numbers.
* Integers have no fixed size limit, they grow infinitely.
* An atom is a kind of value that begins with a `:`.
* Regular expressions are writing like `~r{}` and are Pearl5 compatible.

## System Types

* Underlying resources in the Erlang VM.

## Collection Types

* Collections in Elixir can contain any value in Elixir, even other collections.
* Tuples are encapsulated in `{}` and usually used to pattern match variables.
  * Usually there are no more than 4 elements in a Tuple.
* Lists are linked data structures and not really Array like elements.
  * These are common to Lisp or ML where there is a head(first element) and tail(the rest)
* Keyword lists are a shortcut to key value pairs. Basically a list of two value tuples.
  * `[name: "Bily", sword: "Kapers"] => [{:name, "bily"}, {:sword, "Kapers"}]`
* Maps are collections of key value pairs wrapped in `%{}`
  * Not all keys have to be of the same type.
  * Maps are different than key word lists because they are more efficient as they grow.
  * Square bracket notation is used to access values and dot notation if keys are atoms.

## Functions

* Elixir is very much a functional language. This leads functions to be first class citizens.
* A function has a params list and a body separated with a `->`
  * ex: `fn (a, b) -> a + b end`
* Named functions are innovated using dot notation where anonymous functions are not.
* Parenthesis wrapping params is required during a call but not on declaration.
* Just like regular assignment, Elixir pattern matches params to function calls
  * Because of this Elixir allows one function to execute multiple bodies much like a case statement.
* Underscores can be used as params but do to pattern matching this acts more like a splat, collecting any val.
* 