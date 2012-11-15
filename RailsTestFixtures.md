* Constructor files for TestUnit test Unit/Model tests
* Built in strait YAML
  * Can contain ERB like code though
* Loading is controlled through the `test/test_helper.rb` file
* Great for small projects, however the global-ness of Fixtures becomes unwieldy
  * On larger projects, [factories][0] are a much better choice


[0]: RailsTestFactories