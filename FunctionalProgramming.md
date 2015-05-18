## Notes

* Large idea is point-free or tacit programming. 
  * function definitions do not expose the arguments but,
  * merely compose them.
* Three main functions found in most Functional languages:
  * `map`, `reduce`, `filter`.
  * many other functions are created as a suite for the programmer.
* Create your grammar (composed functions) then use it.
* Highlevel, abstract, declarative.
* Pure functions can exist where a function takes a value and returns the same one.
  * This would be true of a Lodash and Underscore's `_.identity()` function.
  * This also highlights the idea of 'use functions, not values'.
  * So common that it is often called 'k' in functional languages.
* _Referential Transparency_: function only relies on args to for the value returned.