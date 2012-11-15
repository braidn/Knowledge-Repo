##Notes

* Basic way to sort columns when dealing with a lot of results
* gets tacked on to a query after `from database_name`
* `ASC` and `DESC` gets tacked on the end to determine the sort order.
  * by default (if nothing is passed) it is `ASC`

###Via Expressions

* `right (database_column, number)`: sorts by 3 items in from right on
the specified column.


###Via Numeric PlaceHolders

* `order by 2, 5`: when sorting using the returned columns (the second
and the fifth).
