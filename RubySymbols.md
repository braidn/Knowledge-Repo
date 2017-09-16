# Ruby Symbols

## Notes

* Simple, human readable form that "stands for" a specific action.
* One of the few items in Ruby that has a unary delimiter versus a binary
* Not used for data processing
  * therefore they don't have the cacophony of string manipulation methods
* Can only ever be __one instance__ of any given symbol
* Completely immutable (means they will never ever change...not ever, not even if we want it really badly)
* Make ideal hash keys
* The method `to_sym` will change any traditional string into a symbol
* Often times confused as an immutable string.
  * The symbol class never inherets from String
* If you attempt to yank info from a hash that uses symbols with this code: `#{person['name']` you will get an error.
  * Rails is smart and has a HashWithIndifferentAccess class that mitigates this issue
  * `{:a => 1 }.with_indifferent_access["a"] # => 1`
