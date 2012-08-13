A testing suite much like Rspec, focuses on Goal, Role, Feature.

* `Given` lines are the existing pre-condition
  * Capitalizing counts
* `When` lines are describe the action to be taken
* `Then` lines describe the result
* in addition, there is an `And` line that mimics the action specific line above it.
* Happens to be kinda ignorant out of the box about Javascript, so don't worry about it.

###Gotchas

* Make sure to spell things absolutely correctly all the time
* Also keep names down to a minimum throughout your features file.
* The key word `within` is used before specifying some css to look for. More of this in the DSL