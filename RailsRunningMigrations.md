* The most common command being `rake db:migrate`
* Forcing a database to a specific version number is a breeze with `rake db:migrate VERSION=Version#`
  * Version# == timestamp from when the migration was generated.
  * Also works if you want to jump back to the specific migration
* Rolling back the db is easy with `rake db:rollback`
* `rake db:migrate:redo STEP=3` will rollback a migration and redo it.
  * Step parameter is used to rollback and redo more than 1 migration
* Fill your database with data with `rake db:seed`
  * this pulls from the seed.rb folder in the db directory
* Rails keeps track of the last migration run in the db/schema.rb file