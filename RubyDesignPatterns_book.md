#Some stuff from the Book

###Template Method

* Build a base template class in which you can build much more complex
  classes that inheret from base
* Base class can choose to leave methods undefined
  * if they do then specific methods would __need__ to be defined in the
  subclasses
* GoF call this the "template method"
* The abstract "base class" controls the high level processing while -
  * the sub-classes just fill in the details that are pertinent to them
* Very important and it actually bleeds into other patterns
* Drawbacks being this is a very rigid way to develop methods. Changing
[JIT][1] becomes difficult.

###Strategy Pattern

* Define a family of objects that strategically work with each other.
* Objects make decisions on formating at runtime not a process of
inheritance.
  * `some_var = Class.new(SomeStrategy)` vs `class Something < Base:Class`
* Use a chunck of code wrapped in an object (why Ruby is [great for
this][2])
* Code blocks (procs) release the need of building special subclasses.

###Observer Pattern

* Observers subscribe to a class and fire information as the class changes
* Ruby standard lib comes with a completely usable [Observable module][3]
* Observable does not allow the passing of code blocks
* If you write your own methods then you can pass whatever in as a block
	* This creates a proc, looks like a `do/end` block directly after a method call
* Great care needs to be heeded. At its core a method is firing a method on another 
object and that is never 100% fool-proof
* A good example of this is the `before` and `after` calls in ActiveRecord

[1]: https://en.wikipedia.org/wiki/Just-in-time_compilation
[2]: /RubyProcs
[3]: http://apidock.com/ruby/Observable
