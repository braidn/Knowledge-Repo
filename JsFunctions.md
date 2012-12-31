##Notes

* Functions can be called as __named functions__: `function functionName() {};`
* They can also be called __declarative functions__: `var functionName = function() {};`
* Coffeescript only creates declarative functions
* Javascript will scan all named functions first before the rest of the Js code executed.
	* this means that named functions can be in any order
	* where declarative functions must exist _before_ they are called
