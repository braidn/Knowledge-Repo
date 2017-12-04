# Ruby Time

* Ruby keeps three different time based systems.
  1. A programming standard Unix C lib
  1. Ruby Specific Date
  1. Ruby Specific DateTime
* The latter two are much slower than the UNix version...duh!
* ActiveRecord uses the Date/DateTime stuff

## Date OR Time Classe

* There is actually three at work here:
  * `Date`, `Time`, and `DateTime`.
* `Time` is basically the C Time class.
* `Date` can handle more complex/older dates but, has no concept of time.
* `DateTime` Vastly slower at calculations but happy medium between the other two.
* `DateTime` and `Date` are stdlib classes that need to be required

## Month/Day/Year

* Days of the week are represented as an array.
  * An easy way to access the day of the time object: `#wday`
  * There is also a similar way for day of the year: `#yday` 
* There are three available (one alias method) for finding leap years:
  * `julean_leap`, `gregorian_leap`, and `leap`.
  * `leap` being the alias for `gregorian_leap` (most commonly used).
  * All of these are instance methods on the `Date` class.
  * kinda fun fact: Leap Years are ALWAYS devisable by 400
