###Notes

* Debugging is twice as hard as writing the code in the first place
* Manual testing is when you write something, and then you look at the output
* You the programmer are inherently weighted with testing your code
* Cucumber describes behavior of the app
* Rspec test individual modules that contribute those behaviors in Cucumber
* When adding a new feature == new route+new controller method+ new view(unless we can use a previous view.
* Each spec should test just one behavior.
* Use seams as needed to isolate that specific behavior.

###Unit Tests

* Fast, Independent, Repeatable, Self Checking, and Timely.
* The self checking aspect basically deems John White's job useless. Wonder how long that will actually take?
* Rspec is a great tool for building and running unit tests. Due to its complexity it is basically a DSL.
* Spec dir is setup just like an app dir.
* Most of the time we will be writing code for our models and controllers.

###TDD Life Cycle

* Think about one thing the code should do.
* Capture the thought into a test which will fail.
* Write the simplest possible code that lets the tests pass.
* Go back and DRY stuff up.
* __Seams__: A place where you can change your apps behavior without editing the code - Michael Feathers.
* Seams work awesome in testing to isolate behavior of some code from that code it depends on.
* Rspec resets all mocks and stubs after each run.
* Each `it` clause should only do one thing.

###RSpec Test Techniques

* `should_receive(a).with(b)` -should receive something using something.
* `stub` -kind of like should receive but doesn't require to be called, just sits around
* `should` -matches a condition.
* `response` -Rails specific (RC) that hands back the controller response object(s).
* `rednder_template` -RC that enforces the response of a specific view templates.
* `assigns` -RC pass symbol that matches controller instance variable and it returns the value.

###Fixtures and Factories

* _Fixture_: Statically preload some known data into database tables.
* Database wiped and reloaded before each spec with Fixtures.
* This creates dependency on specific fixture data which means breakage is possible.
* _Factory_: create only what you need per-test.
* Helper methods to quickly create objects with default attributes as needed with Factories.
* Complex relationships are sometimes difficult to set up with Factories.

###Stubbing the Internet

* Almost always more than 1 way to do things
* Correct seem depends on focus of the test

###How Much Testing is Enough

* Until time to ship
* 1.2 - 1.5 (Lines of Code/Lines Of Tests)
* Measuring test coverage is kind of difficult subject, check out [SimpleCov repo][1] for more info

###Kinds of Tests

* Unit: model specs.
* Functional or Module: controller specs.
* Integration or System: Cuke scenario
* Unit tests are high coverage with fine resolution, many mocks and no interface testing
* Functional have a few mocks with low coverage, coarse resolution.

###Other Testing Terms

* __Mutation Testing__: if introduction of deliberate error in code, do tests break.
* __Fuzz Testing__: Testing app in ways that it wasn't meant to be used.
* __DU Coverage__: Is every pair <define x/use x> executed.

[1]: https://github.com/colszowka/simplecov