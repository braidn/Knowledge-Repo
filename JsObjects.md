* How to create: JsCreatingObjects  
* JsObjectProperties

###Type Checking

* `typeof object` will return what type of object is being referenced
* `object.has_Own_Property("property")` will return a true or false if the property exists in the object

###Looping

printing out all variables:

     for(var property in nyc) {
       console.log(property);
     }
    for(var property in nyc) {
      var myProperty = nyc[property];
      console.log(myProperty);
    }

###Getters

~~~
inside a class...
this.functionName = function() {
  return this.classVariable;
};
~~~~

###Math

Math object is used to build mathematical operations

* `.abs( )` absolute value
  * great to guarantee positive numbers without using conditional statements
* `.ceil( )` round up to the nearest integer
  * great combined with `.random()*number` to generate a specific random number.
* `.floor( )` rounds down to the nearest integer
* `.max( )` returns the largest of numbers
* `.min( )` returns the minimum or the smallest of numbers
* `.pow( )` returns the power of the number in parens
* `.round( )` rounded to the nearest integer
* `.random( )` returns a pseudo random number between 0 and 1