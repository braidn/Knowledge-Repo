# Ruby Strings

## Notes

* If during interpolation you only need to interpret a single ivar, this syntax works:
  * ex: `#@ivar` versus `#{@ivar}`
* If for some reason someone wanted to delay interpolation, one could use a proc or lambda:
  * ex: `str = -> (someVar), { "some var, #{someVar} set" }`
* The `.succ` method can be called to find the next value in the string.
  * ex: `aaa` becomes `aab`
* By default here-docs are double quoted unless the delimiter is wrapped in single quotes.
* Comparison opertors all compare with ASCII values

## Ruby StringScanner

* Actual standard lib class that can be used by requiring: `strscan`
* Comes with a bunch of fun and interesting ways to scan through a string.
* More importantly than anything it allows someone to know where they are during the scan process.
  * Super helpful to know if we are at the end of a string or if there is more to be searched.

## Handy Methods

* Strings are really arrays of chars so the `[x]` will return a char at the index.
  * this can take a second argument `[x, 4]` and will give you a substring of 4 chars starting at x.
    * ranges can also do the same thing: `[x..4]`
    * even regexes in `[]` are valid
    * this is also aliased to `slice`
* `ord` will return the ordinal code for the char.
  * if this is used on a string, the code of the first char is returned
  * the reverse of this being the `char` method called on an int.
* `encoding` can be used to return the encoding of the string.

### Transformation

* `upcase, downcase, swapcase, capitalize` all do pretty much what would make sense.
* `rjust, ljust, center` all take a value and a char and add this to one side of the string or to the center.
  * `strip, lstrip, rstrip` all remove whitespace from either end of the String.
* `chomp` can take a string for a param and remove that (if it exists) over whitespace
* `succ` will increment a char to the next item in the ASCII table.
