###CLI

* `sudo -u postgres createdb my_site`: create a db
* `sudo su postgres -c psql`: log into postgres command line with
  postgres user
* When connecting locally simply use: `psql -d name_of_db`

###PSQL Prompt

* `\? or \h COMMAND`: Get help
* `\l`: list all databases
* `\d`: list all tables
* `\d+tableName`: describe the table
* `CREATE USER my_user WITH PASSWORD 'password';`: Create a user with a
  specified password
* `GRANT ALL PRIVILEGES ON DATABASE my_site TO my_user;`: Give
  permissions to db 
* `DROP DATABASE db_name;`: Delete a database
* `\timing`: toggle timing for queries
* `alter user username with password ‘new password’;`: change password
* `\c databasename`: connect to a specific database
* `SELECT * from table`: return all rows, must first be connected
* `DELETE FROM tableName;`: wipe a table clean
