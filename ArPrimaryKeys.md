IF using legacy data that doesn't have an ID field here are a few gotchas.

* use `self.primary_key = "column name"` to set the correct collumn
* When saving the row the reference to the id will use the name ID no matter what the column name is. This can be a little confusing
* When referencing the object, use the new name of the column. This is definitely a little confusing.