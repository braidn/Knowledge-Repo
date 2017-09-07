# Ruby Numbers

## General

* Ruby2.4 introduces `.digits`
  * take an integer and explode it into an array of digits.
  * `123.digits => [3, 2, 1]`
* Ruby2.4 introduces a precision arg to many rounding methods.
* `E` and `PI` are actually methods in BigDecimal, not constants.
* Mathn library is a small, 
common lib that allows the myriad of Ruby's numbers to play well together
  * Requires: complex, rational, matrix libs along with itself. 
  * Has a cool way to find the greatest common denominator between two numbers:
    * ex: `36.gcd2(120)`
* Little and big endian refer to importanc of byte order.
  * little: Does the least prominent byte come first?
  * big: Does the most prominent byte come first?
