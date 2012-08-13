Local scope is dictated per function.

* Globals with the same name as local are canceled out by the local
* Nested functions have the power to access variables that are nested in one another
  * Hoisting is when javascript knows that a variable exists in a function but it hasn't been defined yet.
* Although Js has a rigorous block syntax, it does not have a block scope. (like C style languages)
  * this results in the fact that all Js variables should be declared at the top of the function body
* [Scope Chain][1]

[1]: /JsScopeChain