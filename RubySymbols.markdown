* simple, human readable form that "stands for" a specific action.
* not used for data processing
  * therefore they don't have the cacophony of string manipulation methods
* can only ever be __one instance__ of any given symbol
* completely immutable (means they will never ever change...not ever, not even if we want it really badly)
* make ideal hash keys
* the method `to_sym` will change any traditional string into a symbol
* if you attempt to yank info from a hash that uses symbols with this code: `#{person['name']` you will get an error.
  * Rails is smart and has a {{HashWithIndifferentAccess}} class that mitigates this issue