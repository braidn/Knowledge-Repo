##Notes

###Singletons

* Ensures one instance of an object is created and no more
* Best practice:
	* Have a private constructor
	* and a static function that either builds a new object or returns an existing reference
* Traits: basically mixins for PHP
	* Mixed in to a class with the `use` keyword

###Registry

* Global key/value store
	* Examples might be `Reg::set()`, `Reg::unset()`

###Factory

* Augments the new call to a class
* Aids in setting up complex objects or many types of similar objects
* Often times will have a large switch/case statement
	* This aids in creating the specific needs for each object passed in

###Iterator

* Acts much like PHP's existing foreach function
	* except it works on an objects internal data store
* Overides the default foreach behavior in the process
* Most iterator interfaces will have 5 different methods
	1. One that knows the `current()` place in the array
	1. One that holds the key of the current placement
	1. One that holds the next place in the array
	1. One that knows that first place in the array (called `rewind()`)
	1. And one that knows if the object is valid
* There are many iterators in PHP, [check them out][1]

###Observer

* Waits for an event to happen, then fires a series of callbacks
* PHP has its own `Event` class that has methods built in
* Follows closesly to the "First in/First out" idea

###Dependecy Injection

* Allows the consumer of a class to inject specific dependencies
* Often better than a factory because it implements and interface only

[1]: http://www.php.net/class.iterator
