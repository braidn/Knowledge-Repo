* anything can be exploded to an array by passing a splat in front of it
  * like `[*c]`
  * this is the same as passing `Array(c)`
  * hashes act a little finicky
* If an index is asked for but doesn't exist, [nil][1] is returned

###Slicing

* When a slicing index is used that is outside the bounds of the array,
  an empty array ( `[]` ) is returned

###Sorting

* There are times when you will want to sort/group_by and uniq
across a collection of active record objects. 
This can be easily done by the following:
  * `group_by(&:field).values.map(&:first)`
  * The group_by will sort by the field and return a hash,
  * values will omit the keys in the hash and the last map will return a sole selection from the newly minted array.
* `itself` is a method on Kernel that can be used to `group_by` similar items.
  * Say group by a list of similar words: `%w[liger tiger cat tiger] => {'cat' => ['cat'], 'tiger' => ['tiger', 'tiger'] ... }`

[1]: /RubyFalsey