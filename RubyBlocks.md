###Iterators

* Always return a value
* If you have a method you can pass a block to it by encapsulating it with `{ |usableVariable| doStuffHere}`
  * Within the method you can check if a block is given with `block_given?`
  * because this has a question mark it returns either a true or a false value
* Makes good sense to name an iterator block starting with the word `each_`
* calling `include Enumerable` will [embody your class with some powerful collection techniques][0]

###Execute Around

* Used to create routines that are executed before or after something.
* Think of it as handing over the right amount of code at the very specific time it is needed

###Explicit Blocks

* Passed in as a parameter to a method by defining the parameter with a `&`
* After we have captured the block from the params we then call it with a `.call` method in the block of code we are building (__not__ the params)
* These types of of block params allow the creation of pointers so that the block can be called long after the method is finished.
* Be careful because blocks drag local variables along for the ride and hold them in memory __until__ the block is finished (this could be never)
  * get around this issue by `nil`ing out items (like huge arrays) that may be troublesome

[0]: /RubyEnumerable