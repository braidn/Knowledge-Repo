#Solidus/Spree

## Notes

* `store_menu?` used to check if we are in the admin menu
* guest checkout can be set to false in the spree initializers file
	* this and many other settings can be set here (backorders, etc)
	* even things like how many items are shown per page (pagination)
* [Notes on the API][1]

### Routes

* All routes are namespaced with `spree.routeName`
* Uses devise routing names

### Users

* `current_user` works as a check system
* `spree_current_user` is more specific to the Spree system
* add an admin role to a user: `user.spree_roles << Spree::Role.find_by_name(:admin)`

### Models

* Overiding a specific Spree model:
	* `Spree::ModelName.class_eval` block

### Orders

* leans heavily on the state_machine gem
* `checkout_progress` helper method for figuring out where in it the user is
* If orders need to skip certain steps (conditionally per user) than it's easier to set up certain after_transition blocks to the required skipped step that calls `order.next` at the end of the method.
  * ex: `after_transition to: :delivery, do: :someMethod that calls next`  

### PaymentMethods

* Collection of payment methods for a spree customer
* These can be added to by placing new ones in the `app/models/spree/payment_method` dir
* Initialization of each new one is required in the spree.rb config file
 * ex: `config.spree.payment_methods << Spree::PaymentMethod::Name`

[1]: /SpreeApi