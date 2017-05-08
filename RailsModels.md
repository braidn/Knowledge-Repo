# Rails Models

##General

* `dependent => :destroy` forces the association to rely delete it's connection if itself is deleted.
  * this is a little slow if there are a lot of items to destroy
  * another way would be to `dependent => delete_all`
  * if per chance you just wanted to zero out the related id field pass `dependent => :nullify`
* [RailsBelongsTo][1]
* Otherwise known as [ActiveRecord][2]
* Look to add a new model ONLY if a human interface is there to modify data
	* If not, rely on booleans and denormalization
	* Denormalization is where you pull things into models and define dynamic helper methods
* When using boolean columns it is best practices to name them as questions with the same prefix
	* example might be `heard_through_x` and `heard_through_y`  
	* the `:serialize` method works here however becomes inefficient while using
		the find method
* If you wanted to turn a model back into a hash:
  * ex: `someModel.serializable_hash`
* `Delegate` has been a great way to delegate methods to another class.
  * In Rails 5.1, the `delegate_missing_to @klass` was added to delegate everything to the other class.

### Scopes

* Rails4 version: `scope :name -> { where(someFlag: 'active') }`
	* really just stabby lambda syntax, nothing specifically amazing


[1]: /RailsBelongsTo
[2]: /ActiveRecord
