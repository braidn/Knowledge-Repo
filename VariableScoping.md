# Variable Scoping

## Notes

* Usually found in two variants:
  * _lexical_: nearest value to variable lookup wins
  * _dynamic_: use an array and lookup table to stash variable names/values
  * _function_: bindings are relegated to the smallest possible area, this is usually the function.
* The `this` keyword is an example of dynamic binding in Javascript.
