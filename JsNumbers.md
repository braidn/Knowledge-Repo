##Notes

* Floating point values consume twice as much memory as integers
  * Js is smaht and will attempt to change simple FP's to integers where
  it can
* Floating point numbers are accurate up to 17 places after the decimal
* If a number is outside the bounds of Js' numeric range it is
considered `infinity`

###Nan

* Any arithmetic using `nan` returns `nan`
* the `isNaN();` function can be used to check if an object is a number
or not

###Converting to Numbers

* Three ways to do this:
  1. `Number();`: [myriad of rules][1] on what gets changed to a number
  1. `parseInt();`: traverses the string and will search for a possible
     number, more thourough than `Number();`
  1. `parseFloat();`: same as `parseInt()` however it looks for periods
     to create floating point numbers

[1]: https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Number
