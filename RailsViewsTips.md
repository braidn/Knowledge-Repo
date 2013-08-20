##Notes

* With 3.1, make sure to change the password_digest field to password and password confirm
* `form_tag` and `text_field_tag` etc are form tag helpers for not relying on ActiveRecord
  * [API][1]
* `form_for` and `text_field` etc are used to interact with ActiveRecord
  * [API][2]
* Conditional logic can be built using controller name
	* _ex_: `if controller.controller_name == 'something'`

###Collections

* In many instances there is a collection that you will loop over in the view
* Keeping logic out of the views can be done by using the `partial` to render a partial
	* The code could look like: `render partialName, collection: @collectionName` 
	* think of it like the rails partial is being rendered for each item in the collection

###Yield/Content_For

* Yields can take symbols that name them
* in a view you can call: a `content_for :name` block and the content will show up in the yield
* This technique can be used in class/id names or really anywhere
* Defaults in this category are a little weird: `yield(:name) || 'SomethingElse'`
* A logical if can be used as well: `if content_for?(:name)`

###CSS

* If you wrap classes in a array you can write:
	* `<< ('otherClass' if something == something)` to make things a little dryer

###Pitfalls

* Domain logic code likely belongs in your model and not in a helper(accesed by controllers/views)
* Avoid jamming all your helpers into the global ApplicationHelper file
	* this also can mitigated by dumping helpers per controller and going to a helper per 'area' idea

[1]: http://api.rubyonrails.org/classes/ActionView/Helpers/FormTagHelper.html
[2]: http://api.rubyonrails.org/classes/ActionView/Helpers/FormHelper.html
