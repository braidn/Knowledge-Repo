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
* A Simple map implementation could be created by doing the following:
  * `myMap([tail | head], fun), do: [func.(head) | myMap(tail, func)]`
  * `myMap([1,2,3,4], fn (x) -> x*2 end # [2,4,6,8]`
  * a shorthand for above is: `mmap [1,2,3,4], &1(&1 * 2)`
* An incrementor or an 'invariant' can be passed in the second argument.
  * This is often times used to carry state around from one iteration to the next.

## Iex Prompt

* Wrap a function/item in `h()` for help.

## Lists

* Created much like arrays in most other languages
* The assignment operator can cast a list onto another list.
  * This would assign each of the characters of the second list to each of the first.
* Have the concept, like many functional languages of `head` and `tail`
* If all values in a list represent printable characters, then elixir will output the word.
  * This can be thought of as strings in ruby. Each char has a specific list/array location.
* Because of the head/tail idea, many lists will go through a form of recursion.

## Dictionaries

* Just like in many other programming languages, these are simple key value pairs.
* They come in a variety of flavors: HashDict, Maps, and keywords.
* Maps and HashDicts implement the `Dict` behavior.
  * The Dict module will have plenty of methods to modify and change Dictionary types.
* To access a specific values, use an atom like: `dic[:key]`
* Multiple identical keys are allowed but require some special getters to get information.
* Like most things in Elixir, pattern matching plays a big role in Maps.
* Maps do not allow binding of a value to a key during pattern matching. 
* Like most things in Elixir, Maps are immutable and updating one cause a new copy.
  * can be done by: `new_map = %{ old_map | key => val }`.
  * all assignment changes happen after the pipe operator.
  * this is _only_ for changing existing keys, not removing or adding.

### Struct

* A struct is a lightweight version of a map and allows for type pattern matching.
* Structs are wrapped in modules to have struct specific functions defined to the associate struct.
* Structs are accessed using dot notation: `something.name`
* These are seemingly good for adding types like in Elm or Golang.
* Structs can also be nested within one another. The field would take: `%{}` as a type.

### Sets

* Only one implementation of sets: HashSet

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
* Scope is defined within the function and acts much like a clojure, binding all params to connected functions.
* `&` operator converts the expression into a function where `&1` and `&2` are params
  * This ends up being a great solution to pass functions to other functions
  * Ex: `Enum.map [1,2,3], &(&1 + 1)` as a simple list incremented
* Functions are identified by there name and their rarity.
* A private function is defined using the `defp` keyword

### Function Body/Block

* Underlying Elixir code for the block looks like: `def method(n), do: n * 2`
  * Any amount of lines, using () can be passed to ().
  * `do/end` blocks are just syntactic sugar and at compile time get morphed into the above.
  * The do syntax makes it look much more lisp like with multiple functions and args passed inline
* Function calls follow the same kind of pattern matching that the `=` sign does.
  * This means you can have multiple functions named the same with diff arity without raising an error.
* This kind of programming is known common in functional languages.
  * An anchor is created which is inherently easy
  * A recursive function will end up calling the anchor and breaking the function calls.
  * Order of these functions matter, Elixir looks from the top down.
  * These types of functions should be grouped near each other in the file definition.
* Guard clauses can exist in the method definition itself.
  * ex: `def is_awesome(n) when is_atom(n) do`
  * Handy way to control whether a recursive function will be called through pattern matching.
  * There are is a limited amount of expressions that function in guard clauses so be careful.
* Default params are a possibility using: `param \\ default value` syntax`.
* Private functions are defined using the `defp` syntax over the `def` syntax.
* `|>` operator takes the result of the expression on it's left and passes it to as the first param to the function on it's right.
  * This is also called a 'pipeline'.
  * ALWAYS put parens around function params in pipelines.

## Modules

* Used to namespace functions and wrap macros, structs, protocols, and other modules.
* There are several directives for modules [`import`, `alias`, `require`].
  * All directives are lexical scoped so their scope will be within the module definition (usually).

### Import

* Imports the functions or macros into the current scope. Used to stay dry.
  * ex: `import Module [, only:|except: ]`.
* Second param is a list of imported functions and their arity: `[flatten: 1]`.
* This allows the programmer to be specific with what is imported versus taking everything.


### Alias

* Creates an alias of the module.
  * ex: `alias Mix.Tasks.Set, as: Set`.
* Cuts down on the amount of namespacing code required when writing/calling functions.

### Require

* Only used when one wants to use macros defined by the specific module.