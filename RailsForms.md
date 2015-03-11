### Rails 3

By default, all forms use the post http method.

* {{RailsFormHelpers}}
* When dealing with RailsSessions make sure to add the `_tag` on to each label and field declaration
  * This tells rails that the information isn't going to be saved in a database

### ReForm

* Library that extrapolates form objects for easier processing
* Framework agnostic
* Can sometimes throw errors with Rails4 ([more info at repo][1])

[1]: extrapolates