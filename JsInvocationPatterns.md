###Method Pattern

* When a function is defined as a method on an object

~~~
var Object {
  billy: function(param1, param2) {
};
~~~~

* `this` is used to retrieve or modify values within the object
  * called public methods

###Function Pattern

* Defining a function outside of an object.
* `this` works very odd in these functions, it is bound to the global object over the function itself.

###Constructor Pattern

~~~
var Quo = function(params) {
  this.status = params
};
~~~~

* Then you could use the word new to inherent from this newly defined object.

###Apply Pattern

* Utilizes the `.apply` method that takes two parameters
  * 1st is what get's bound to `this`
  * 2nd is an array of of the actual params