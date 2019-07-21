# Ecto

## Notes

* ActiveRecord like interface for Elixir apps.
* `Ecto.schema` is the function used to define specific field in the DB.

## Migrations

* Migrations are written very similar to ActiveRecord.
  * `add` function takes two atoms (one being column name other column type).

## Commands

* `mix ecto.create` create the DB defined in the config.
* `mix ecto.gen.migration migration_name` create a migration file.
* `mix ecto.migrations` displays a list of migrations and if they are applied or not.
* `mix ecto.migrate` migrates the db all the way forward.
* `mix ecto.rollback` migrates the db back since the previous migration.
