##Notes

* `show databases`: to get a list of all databases
* `use database`: connect to a database for querying
* `desc table`: shows how the table's columns, constraints, etc
* When using foreign key constraints the system blocks the user from
using an id that doesn't appear in the referenced table.
* Default date format: YYYY-MM-DD
  * str_to_date function can be used to tell the db the format of the
  date string
  * achieved by: `str_to_date('DEC-21-1980' , '%b-%d-%Y')`
* `drop table tablename`: kisses it all goodbye
* `mysql -u root -p dbname < *.sql_file`: importing a .sql file
* Views are often known as virtual tables
* [Filtering][6]
* [Joins][7]
* [Sets][8]

###Inserting Things

* 3 main things when using inserts
  1. The name of the table
  1. The name of the columns
  1. The data to be placed in the columns
* [Example][1]
* The amount of columns provided and values must line up or errors will
be thrown
  * This goes for the specific value types

###Selecting (AKA Touching) Things

* [Example][2]
* `order by` option specifies the order of the returned values
* Query Clauses: `select`, `from`, `where`, `having`, `[group by][4]`,
`[order by][5]`
* Column aliases can be added to select statements after each column
name. A space is needed but no quotes
  * The `as` keyword can also be used to create aliased columns
* By using the `distinct` keyword like `select distinct` you remove any
duplicate data.

###Altering The State of Affairs 

* `alter table tablename modify column extra options`: simplest way to
update data
* [Update Data Example][3]
* when using `where` to select records, one can use less than and
greater than symbols to update banks of records

###Punting Items Outa-Here

* `delete from tablename where id = #`: Simple and svelte way to remove
records
* if removing a column:
  * `alter table table_name drop column column_name`
  * or `modify table table_name drop(column1, column2, column3)`
* Guarenteed POOF!

###Null

* Like most languages, null is simply the absent of a value in a field
* Two nulls are never equal to one another
* Something can be null, but it can never _equal_ null
  * this means this: `where id is null` works
  * and this: `where id = null` doesn't work
* Sometimes you want to search for null because the results match your
structured query
  * example would be who doesn't work for X: Well technically if you
  just searched who's employee id isn't X your results would be off if
  there are any null's in this column

[1]: /SqlInsert_Example
[2]: /SqlSelect_Example
[3]: /SqlDataUpdate_Example
[4]: /SqlGroupBy
[5]: /SqlOrderBy
[6]: /SqlFiltering
[7]: /SqlJoins
[8]: /SqlSets
