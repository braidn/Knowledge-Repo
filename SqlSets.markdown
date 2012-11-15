##Notes

* There are some rules involved
  1. Both data sets must have the _exact_ same amount of columns
  1. Data types of each column across the sets must be the same or
     changeable by the server into a correct format
* Order by queries __must__ be used with column names from the first table

###Union Operator

* `union` and `union all` combine two sets of data
* `union` will sort the two sets and remove dups where `union all` will
not

###Intersect Operator

* Intersect is not built into mysql 6.0
* Uses the `intersect` terminology
* Just what one would think, used to search for a piece of data that is
apparent in both tables
* Just like with `union` the `intersect all` does not remove duplicates

###Except Operator

* MySql 6.0 does not support this opperator as well
* Returns data from the first table minus any overlap that the first
table has with the second.
