##Notes

* Usage boils down to using the `where` flag
* When using three or more `or` `and` conditionals it makes more sense
to wrap things in parenthesis. This also adds to overall readability.
* the `not` operator can be used before parenthesis and works like it
should in normal logic
  * `not` is often times hard to read and can be prepended by using
  `!=` when dealing with specific columns
  
###Equality Conditions

* `column = expression`
* a direct opposite of this condition would be the inequality condition.
  * basically `column != expression`
  * this can also be written as `column <> condition`
* These conditions are often used when modifying data.
  * think removing a bank account if it was_closed > 2.years.ago

###Range Conditions

* does x fall inbetween two items (pretty self explanatory really).
* utilizes the logic `< > <= >=`
* The `between` operator bridges the need of lots of symbols:
  * `where some_column between 'some date' and 'some other date'`
  * one _catch_ always make sure to select the lower limit of the range
  first.
* When working with ranges concerning strings, you need to how the
string is built. A good example would be think of Social Security
Numbers.

###Membership Conditions

* Used when looking for a finite set of values.
* The `in ('something', 'something')` operator allows the user to string
`or`s together without the repetition 
* With most things, the `not in` reverses the `in` logic

###Matching Conditions

* Where you only know a little bit of what you are searching for.
Perhaps the first letter of the word.
* _Wildcards_ can assist when you are trying to narrow your search
  * `_` used in place of __one__ character
  * `%` used in place of any amount of characters
* full search: `where some_column like '_a%e%'`
* using `or` and `and` is great for narrowing searches
* If the sql variant selectors fall short regular expressions are legit
using the `regexp` operator
  * full syntax: `where some_column regexp 'some[regexp]'`
