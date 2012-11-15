* A snippet of code that gets called to tell the user that something has happened or will happen

###Examples

* defining a new class level method (`def self.MethodName`) named `inheritance` will fire off some code when a class is subclassed
* `at_exit` hook gets fired right before all of the Ruby code goes out the window.
  * key for hooking things up to fire as the code exits
  * instead of most hooks that are simple overrides, `at_exit` gets called as a do block
* hooks on `method_missing` are fairly common in the Ruby world
* `set_trace_func` will fire after any line of code completes...__ANY__
