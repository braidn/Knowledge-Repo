#Ruby Procs

###Notes

* On a basic level, it is a way to store methods in a variable.
* Can be created by Proc.new or just adding proc before the a block
  * If ruby 1.8, calling just `proc` will fire up a {{RubyLambda}} and not a true proc
* 4 different ways to call a proc
  1. `myproc.call(10)`
  2. `myproc.(10)`
    * Synonym for the `.call` method
  3. `myproc[10]`
  4. `myproc === 10`
    * Iteration of the case statement and able to be applied directly to when statements in the overall case statement
* The do and end items can be substituted for `{}` which make it more
Javascripty in my mind.
  * Although the norm is to use `do` and `end` with multiple line blocks and `{}` on single line blocks
* parameters are called between the pipes like: `lambda {|para1, para2|}`
  * and passed after the `.call` method in parens separated by commas

###Performance

* It is common for someone to create a proc and call a method with it versus yielding to an enumerator in a block.
  * This is somewhat more elegant but, since Proc's are Objects, the proc method is much slower.
  * This also aligns nicely with the idea that Ruby is not Javascript...
    * so we have blocks, use them and avoid passing around functions indiscriminately. 