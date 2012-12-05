##Notes

* JS is made up of 3 separate parts: Ecma, the DOM, and the BOM
* DOM created by the W3C because they feared that MS and Netscape would
splinter the web into two separate camps.
* BOM deals with moving, creating, resizing viewport windows.
* ECMAScript identifiers use camel case (`stuffIsAwesome`) therefore it
is good to keep to this standard when building identifiers(variables) in Js.
* Reserved words currently should be from ECMA3 + `let` and `yield`
* There are 5 data types or primitives: Undefined, Null, Boolean,
Number, and String
  * there is one complex type called: Object. It is an unordered hash
* Since JS is loosly typed, there needs to be way to figure out a type
of something 
  * this is done by `typeof(object)` operator
* Uninitialized variables get auto kicked to the curb as `undefined`
  * undefined and undeclared variables (different) will post `undefined`
  if asked their `typeof()` 
  * `undefined` is a derivative of `null` therefore if they are asked if
  equal, they will return true
* [Boolean Types][1]
* [Number Types][2]
* [String Types][3]
* [Object Types][4]
 
[1]: /JsBoolean
[2]: /JsNumbers
[3]: /JsSrings
[4]: /JsObjects
