__Definition__: a method defined for exactly one object instance.

* to create one, instead of a regular `def method_name`, use `def name_of_instance.method_name`
  * for example if we created a new Object called `gimme_bar` you would send a def call to `gimme_bar.coma` to send the gimme bar into a coma
* an alternate way to call the methods would be to initiate the new object then use a block `class << name_of_instance` and add traditionally built `def` methods within.
* Methods built in a singleton class will win out on any other methods up the chain
  * this is due to the fact that singleton methods are like herpes. They stay dormant until you absolutely need them.
*_Remember_ singleton methods are great for playing with instances, class methods will always throw errors.