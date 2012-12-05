##Notes

* True is not equal to 1
* False is not equal to 0
* Boolean literals are case sensitive
  * Using `True` as a variable is totally legit, if not stoopid
* One can easily turn any object into a boolean by calling `Boolean();`
  * Flow control statements (if) auto create this

###Operators

* Comprised of `NOT` `AND` and(coincidence!) `OR`
* `NOT` converts the operand to a Boolean than negates it
  * This would mean that `!!` would return the Boolean of the operand
* `AND` like in many languages is a short-circuit operand...
  * meaning that if the first object is true, it auto returns: `true`
  * `OR` works in exactly the same fashion
* Using `OR` this example is often seen in js code (fallback variable
assignment)
  * `var something = iWantThisValue || fallbackValue;`
* Many comparison operands use character codes to evalutate themselves
  * this would mean that `B < a` since all uppcased leters are lower
  character code wise than lowercase letters
* Identically equal(`===`) is different from equal(`==`) because it
compares both objects before type cohersion
