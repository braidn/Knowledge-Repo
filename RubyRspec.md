###Notes

* `should` and `should_not` are the dominant verbs in Rspec. These are sometimes called "specification predicates" a big list of them can be found at the [rspec website][1]
* create stubs and mocks of objects with `stub_name = stub :methodName1 => 'response', :methodName2 => 'response'`
* `.stub!` method also available that allows the tester to stub out methods on any normal object.
  * `object_name.stub!(:methodName)`
* a good way to learn how to properly implement rspec is reading [Rubyspec.org][2]

###Syntax

* `let(:method){}` used instead of before each if only creating instance variables for it blocks
* `describe()` is used to define an example group
	* `context()` is an alias of describe
	* it is used to define contexts rather than describe which describes things
* `it()` is used to define a single code example
	* each `it` block will likely be with a describe block
* three different kinds of hooks are provided:
	* `before(:each)`, `before(:all)`, `after(:each)`, `after(:all)`, `around(:each)`

###Best Practices

* Keep clear the methods you are describing using `.` for class and `#`
for instance methods.
* Spec descriptions should never be longer than 40 characters
  * If they need to be split them using a context block
* One assertion per test
* When describing tests use the third person in the present tense.
* Many people use double quotes in `it` statements although there is no magic needed

[1]: http://www.rspec.info/
[2]: http://rubyspec.org/
