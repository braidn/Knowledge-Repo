##Notes

* One of the simplest ways to do many to many relations

###Requirements

* when calling the method in the models, use the plural form
* the join table is the concatenation of both classes
	* the greater table will be first so Developers/Projects = developers_projects
	* again both using the plural form
	* `add_index :tableName, :reference_id` should be used for each reference item
	* `, id: false` passed in the `create_table` block because no Id's are needed
* Act on the relation like an array
	* `[Item1.find(:id)]` or `<<` to push items into the array
