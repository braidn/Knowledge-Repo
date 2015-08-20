This is a small amount of snippets when testing.

### TestUnit

* the /test/test_helper.rb is generated on build and included in all test files
* best to create a module for setups in /test/setup_methods.rb
  * Include the module and call `setup :setup_method_names` when needed in tests.
  * the `setup :method_name` is much like before/after_filters

### Rspec

* [Ruby Rspec][1]

### Cucumber

### Engines

* Routes in engines can cause some issues, especially spree
* It's [best to define the @route ivar in the test file][2]


[1]: /RubyRspec
[2]: https://github.com/spree/spree/commit/bd881d9d34e418eeb73a30440013bfeb31ebea45