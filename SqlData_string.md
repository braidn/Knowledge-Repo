##Notes

* Always wrapped in quotes
* Three different common types:
  1. Char
  1. Varchar
  1. Text
* Only Oracle and MySql servers are capable of escaping with a `\`
  * Others are escaped with another single quote
* MySql has the `quote()` function that will return escaped characters
(clean) characters
* `select char(<ascii_number>)`
* `select ascii(<anything>)` will output the ascii code for the
symbols/letters. Works on individual letters

###Manipulation

* `select length(<column name>) <return name>`: returns the length of
the column data
* `select position('<string>' in <column_name>)` will return the
numerical value of where <string> begins
* `strcmp('<string1>', '<string2>')` will compare two strings to see if
they are equal
  * This function only works in MySql
* `concat(<db_selection>,'<string>')` will do exactly what it sounds
like
  * It can also be used to build strings for output
* `select insert('<string>', <start>,<end>,'<string_to_add>')` inserts
the second string into the first at the start and end points
* `select substring('<string>',<start>,<end>)` selects just the
substring defined by the start and end points
