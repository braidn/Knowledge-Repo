* Sub classes of Active Record::Migration
* `add_column` used in raising tables and `remove_column` used when dropping
* Handy graphs detailing migration types in Agile Web Development 4th edition, page 384
* `rename_column :model, :originalName, :newName` is handy when you fuck up a name.
* `change_column :model, :columnName, :newType` changes the specific type of the column.
  * When downing change columns, if the data is incompatible it will be thrown away.

* `rename_table :old_name, :new_name` for when you fuck up spelling a table...which happens
* Supported Migrations: