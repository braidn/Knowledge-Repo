This is a small amount of snippets when testing.

###TestUnit

* the /test/test_helper.rb is generated on build and included in all test files
* best to create a module for setups in /test/setup_methods.rb
  * Include the module and call `setup :setup_method_names` when needed in tests.
  * the `setup :method_name` is much like before/after_filters

###Rspec

###Cucumbrt