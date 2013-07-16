##Notes

* Pass a `:name, :arrays => true` when creating the migration
* Active record will not specifically track the destructive changes
	* Pass `object.nameOfArray_will_change` before a `save` AR call
* Arrays may have sub arrays but they must contain the same number of items
	* this means some might have nil placeholders
