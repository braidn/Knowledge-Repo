# Ruby Regexp

## Notes

* if nothing is found then nil is returned
  * __not__ a number
* Uses the `=~` operator to match a string to a regular expression
  * don't get it confused with `==` which has no bearing here.
* `^` used to search at the beginning of a string or the beginning of any line
  * kinda like using `\A`
* `$` the exact opposite of the ^. These two are very reminiscent of the vim key bindings 
* In Ruby2.4, `.match?` is implemented to return just a boolean.
  * It does not allocate memory at `$ ~` for match data(drastically speeding things up)
* Fully Unicode aware. They match characters rather than bytes.
