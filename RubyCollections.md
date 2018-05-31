# Ruby Collections

## Arrays

* anything can be exploded to an array by passing a splat in front of it
  * like `[*c]`
  * this is the same as passing `Array(c)`
  * hashes act a little finicky
* If an index is asked for but doesn't exist, [nil][1] is returned
* When creating an array using `Array.new(x)` a block can be passed
  * elements of the array are created using this block over just returning x nils
* When using `Array.new(x, thing)` each element is x of the same object
  * this isn't true with the block notation

### Slicing

* `unshift` adds items to the beginning of an array where `push` adds to the end
  * crocodile or shovel or `<<` op is way more common over push though
  * `shift` and `pop` perform the opposite and remove items from the front or back.
* `values_at` acts just like `slice` and `[]`.
* When a slicing index is used that is outside the bounds of the array,
  an empty array ( `[]` ) is returned

### Sorting

* There are times when you will want to sort/group_by and uniq
across a collection of active record objects. 
This can be easily done by the following:
  * `group_by(&:field).values.map(&:first)`
  * The group_by will sort by the field and return a hash,
  * values will omit the keys in the hash and the last map will return a sole selection from the newly minted array.
* `itself` is a method on Kernel that can be used to `group_by` similar items.
  * Say group by a list of similar words: `%w[liger tiger cat tiger] => {'cat' => ['cat'], 'tiger' => ['tiger', 'tiger'] ... }`

## Hashes

### Notes

* Ruby 1.9 introduced ordering into Hashes.
  * previously hashes had no idea about ordering of elements (first/last/etc)
  * this means that methods like `each_with_index` were impossible prior to 1.9
* Ruby 2.4 introduces `transform_values` that iterates over each key and does something with the values.
  * A method that was actually extracted from Rails.
* Hashes can be created usign `Hash[array of strings]`
  * This array must be an even number (key value pairs) else an error is raised.
* `values_at(hashKey1, hashKey2)` will return an array of values for each key provided as args.
* A param can be passed to `Hash.new(x)` where x will be returned if a key not in the hash is attempted access.
  * if a block is passed to `Hash.new` turns into the default value for new keys

### Merging / Transforming

* `update` is the destructive version of `merge`
  * this also means that `merge!` is a synonym for `update`

[1]: /RubyFalsey
