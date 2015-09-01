# Elixir

## Notes

* `ex` files are compiled to bytecode
* `exs` files are more for scripting and not compiled. These are usually reserved for tests.
* Assignments with the = operator are considered matches.
  * Elixir attempts, in all ways possible, to make the left side values the same as the right.
* Elixir's pattern matching allows reassignment where Erlang's doesn't.

## Iex Prompt

* Wrap a function/item in `h()` for help.

## Lists

* Created much like arrays in most other languages
* The assignment operator can cast a list onto another list.
  * This would assign each of the characters of the second list to each of the first. 