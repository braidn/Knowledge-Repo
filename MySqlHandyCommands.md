###Notes

* Foreign keys are easily created and managed by:
	* `foreign key (columnName) references tableName (tableName_id that it references)`
	* this can be performed as `alter table` or after defining the column when creating the table
	* this adds a few constraints where ids can not be added if they don't exist
* When using transactions, it only works with tables created using `engine=InnoDB`
* `count()` function is grouped in a special class called: _aggregate-functions_

###User Management

* `create user`, `grant`, `revoke user`, `rename`, `set password`, `dropuser`, `flush`, `show grants`, `show privileges`
* Easy way to create a user: `create user *username* identified by *password*`
* Depending on the age of MySql sometimes you need to revoke all
privledges before dropping a user
* `usage` keyword is used to modify the resources a user can use and
will _not_ modify their existing privledge set.
* `rename user1 to user2` will do what makes sense but _won't_ change
their existing privledge set.
* `change password for user = password('new password')` to change
passwords
* `select user, host from mysql.user;` will output a list of available users
