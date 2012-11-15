###Notes

* There is no other time but run-time
* Objects have types but variables don't
* symbols are immutable strings with value of itself
* Ruby has no declarations when it comes to variables

###Regexp

* if no match then the value is false
* if there is a match then value is non false + you can search through capture group with `$1..$n` variables

###Objects and Methods

* Methods can be written with `.send(:someMethod)` without writing the dot syntax
* Since everything is an object the language itself is built around the above the send method
* This also means that self is always set to something
* `a.b` is read __call__ method b on _receiver_ a
* Idiomatically, all method names are symbols but can be written as a string

###Hashes and Arrays

* it is ok to omit hash braces when the very __last__ argument to the function is a hash (think link_to helpers in Rails)
* Use parenthesis and hash braces defensively
* The interpreter will likely tell you where you went wrong

###Classes and Inheritance

* class construction begins with `class ClassName` and can take an optional `< InheritanceName`
* __NO__ multiple inheritance, only mixins
* `initialize` function is what is called when `.new` is called on the class
* instance variables are prefaced with an @ sign
* Methods ending with = are mutators or setter methods
* @@ are reserved for class variables or static variables
* `self.methodName` creates a method for the specific class, not the instance of the class

###MetaProgramming

* Crack open an existing class and add in a new method call
* Most of the time these method calls will utilize the `self` idea to modify items
* method_missing is super handy

###Blocks

* Sometimes known as expression orientation
* most of the methods have a safe and unsafe method

###Mixins and Duck Typing

* Modules are a collection of class and instance methods that are not a specific class
* Interesting Modules mixin a certain amount of methods
* Method missing looks at inheritance then any modules
* Modules kickass at reusing high level behavior
* Modules usually used a lot more frequently over inheritance

###Yields

* Blocks are closures: they haul their environment around everywhere.
* Allows sending code to where an object is rather than just passing an object to the code