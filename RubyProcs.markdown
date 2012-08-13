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