##General

###Controllers

* Some people feel like instance methods should ONLY be declared in "action blocks"
	* this would mean that anything under private/protected would be a no-no
	* this can even be extended to parameters as well
* `respond_to` blocks can be written like `before_action` above all action blocks
	* and example: `respond_to :html, :js, :json`
	* in each block you would use `respond_with(@instanceVar)` methods, keeping things
	'DRY'
* When dealing with fields for other controllers or 'nested fields' use `fields_for`
	* an example: `<%= f.fields_for :modelName do |a| %>`
	* in the correct model there needs to be a call to: 
	`accepts_nested_attributes_for :modelName`
	* as an added bonus validation (if any) will occur on both models
	* in the controller: `@item1 = Item1.new(:item2 => Item2.new)`
* ownership actions (`current_user_id`) should be assigned in the controller
	* instead of being fired in a hidden field in a form
	* this is for security reasons: users can't assign forms to other users

###Presenters

* Used to abstract unweildy and instance variable rich controller actions
* Sometimes an additional load path is needed if using a separate var
* Just ruby classes with namespacing, initialize and other methods
* The presenter _1st_ gets called into an instance variable in the controller
	* then the instance var is called in the view with the correct presenter method
	* presenters are heavy users of ActiveSupport::Memoizable due to their heavy caching
* [More][1]

###Models

* When dealing with scopes, remember Rails makes them a method on runtime
	* this will cause wheres with time to never change after they are first run
	* this is easily fixed by making the scope a lambda therefore it gets evaled
	every time the method is fired
* When dealing with SQL, always use the `?` syntax to escape user input
 * passing hashes or symbols that relate to hashes is as safe as the `?` op

[1]: /RailsPresenters
