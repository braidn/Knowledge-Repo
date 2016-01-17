# Handy Ruby Methods

* `arity`: will output a number of the params that a method or proc takes.
* `break :val`: acts a lot like return on a specific value which can read better/easier.
* `&.` acts like `try` method and will return nil over a no method error. 
  * This is also known as the lonely operator and only works in Ruby 2.3 and greater.
* `retry`: used in a rescue block to retry the code that errored out.
* `case ===`: the comparison op in case is always the three-equals method.
* `String#chars`: easiest way to get a string into an enumerable object (array of characters).
* `String#up_to`: build an array of chars from the char the method is called on to the param.
* `lazy`: allows you to create a lazy array and use `next` to count through it.
* `Enumerable#detect`: will return the first item that is true from the block.
* `Method#owner`: best way to find where the method is defined in the ancestors tree.
* `!!`: evaluates the truthiness of an object. (`!!nil => false`).
* `Number#succ`: get the next number if performing an `+1` op.
* `included_modules`: handy way to get a list of included modules on the object.
* `1.0/0`: cleaner/easier/shorter way to define infinity.