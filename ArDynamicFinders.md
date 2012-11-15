* `find_by, find_all_by, find_last`
  * All of these will be followed with a _columnName("searchTerm")
  * there is also the ability to chain them together like `find_by_columnName_and_columnName(cn1, cn2)`
  * if there was a search in which you wanted something to occur you could use one of these two finders:
    * `find_or_initialize_by()` which sets a new state in the db
    * `find_or_create_by()` which calls a create action on the db
* Sort of like constructing SQL queries but more simple, and much easier to read  
* appending a bang(!) like this: `find_by_name!("Dave")` will throw a {{RecordNotFound}} error instead of nil