###Notes

* Classes are sort of hacked together through the idea of constructor
functions.
* A person class might look like `var Person = function(*args) {};`
* The word 'class' is reserved in Js so it is often aliased to '_class'
or 'klass'
* `arguments` var is special in that it is a sudo array of arguments
that have been invoked in the current scope

###Event ordering

* Basically the opposite from Moz/Ie
* IE implements the inside out model "bubbling model"
* Mozilla works with the outside in model "capturing model"
* W3c gave the builder the function to call which ever event ordering
made most sence to them.
* `somevar.addEventListener("click", function(stuff){};, true)` = event
listener invocation
* If the last argument is set to `true`, then capturing is used and if
it is `false`, bubbling is used. (easy)
* Fairly _normal_ to use `false` as a default.

###Adding Functions to Classes

* To add an class function simply use dot notation.
* Example: `Person.find = function(x) {};`
* To add instance functions the 'prototype' keywork is required
* Example: `Person.prototype.find = function(x) {};`
* It is common to alias instance function creation from prototype to
'fn'
* Example: `Person.fn = Person.prototype;`
* However, you would need to do this aliasing on each individual
class(klass)

###Items to explore more

* `call()` and `apply()` functions
