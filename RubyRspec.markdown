###Notes

* `should` and `should_not` are the dominant verbs in Rspec. These are sometimes called "specification predicates" a big list of them can be found at the [rspec website][1]
* create stubs and mocks of objects with `stub_name = stub :methodName1 => 'response', :methodName2 => 'response'`
* `.stub!` method also available that allows the tester to stub out methods on any normal object.
  * `object_name.stub!(:methodName)`
* a good way to learn how to properly implement rspec is reading [Rubyspec.org][2]

###Best Practices

* Keep clear the methods you are describing using `.` for class and `#`
for instance methods.
* Spec descriptions should never be longer than 40 characters
  * If they need to be split them using a context block
* One assertion per test
* When describing tests use the third person in the present tense.

[1]: http://www.rspec.info/
[2]: http://rubyspec.org/
