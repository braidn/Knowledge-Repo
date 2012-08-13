4 methods that take the cake:

1. `.eql?`
1. `.equal?`
    * tests for object identity
    * `x.equal?(y)`
    * read x object is equal to y object?
1. `==`
1. `===`
    * {{RubyCaseExpression}} normally use this operator to find the specific case

### Other Methods

* The `.instance_of?` method will return true if is an instance of the direct class (no inheritance allowed)
  * The `.kind_of?` method will allow inheritance chain lookups
* The `respond_to?` method will see if a class response to a specific class within the method

### Duck Typing

* it is often best to create a method that tests equality instead of overwriting how the `==` works.