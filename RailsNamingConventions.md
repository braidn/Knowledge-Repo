Many of the below are either conventions in Ruby or directly bleed into it.

* Convention = all lowercase / separated by underscores
* Classes and {{RubyModules}} use CamelCase
  * not camelCase
* Table names are underscored, lowercase, and always plural
* Model names would be written as LineItems and reference a table called line_items
* Controllers will always (unless removed) have a corresponding Helper
* Unlike Ruby there is no need to use the require keyword.
  * If a class is used that is unknown the the name is deconstructed and a corresponding file is looked for in the background.