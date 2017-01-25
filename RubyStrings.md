# Ruby Strings

## Notes

* If during interpolation you only need to interpret a single ivar, this syntax works:
  * ex: `#@ivar` versus `#{@ivar}`
* If for some reason someone wanted to delay interpolation, one could use a proc or lambda:
  * ex: `str = -> (someVar), { "some var, #{someVar} set" }`
* The `.succ` method can be called to find the next value in the string.
  * ex: `aaa` becomes `aab`

## Ruby StringScanner

* Actual standard lib class that can be used by requiring: `strscan`
* Comes with a bunch of fun and interesting ways to scan through a string.
* More importantly than anything it allows someone to know where they are during the scan process.
  * Super helpful to know if we are at the end of a string or if there is more to be searched.
