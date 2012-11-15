##Notes

* Basic method for linking two or more tables together through a query
* Always used with `join` keyword
  * example: `from employee e join department d`
* When performing `select` statements it is best to alias the tables
like seen above.
* Because Sql is a nonprocedural language, the server determines in what
sequence is best for joining multiple tables together.
* Where Join Conditions and Filter Conditions are being used make sure
to make things readable
  * This is a requirement because "generally" the order of these two
  items doesn't matter to the server

###Inner Joins

* Occurs where the join depends on a foreign key between two tables
* Should use prepend the word `inner` to the join phrase to be clear
  * `inner join`
* Most servers default to the inner join if nothing is specifically
called
* If the names used to join the tables are idential you can use `using`
instead of `on`
  * `using (dept_d)` instead of `on e.dept_id = d.dept_id`
* A three table join will include two `join` types in the from clause
  * along with two `on` subclauses
  * [example][1]
* Best way to think of a > 2 table join:
  * the first two tables get the ball roling and each subsequent join
  gets tacked on as the ball continues its ride down the hill
  
###Self Joins

* Returning a set of information where one table is actually joined to
itself

###Equi / Non Joins

* In many cases, joins will be done by an `=` sign (equi). However, this
is not a requirement, joins can be done via  a range (non equi joins)

[1]: /SqlThreeTableJoinEx
