* anything can be exploded to an array by passing a splat in front of it
  * like `[*c]`
  * this is the same as passing `Array(c)`
  * hashes act a little finicky
* If an index is asked for but doesn't exist, [nil][1] is returned

###Slicing

* When a slicing index is used that is outside the bounds of the array,
  an empty array ( `[]` ) is returned

[1]: /RubyFalsey
