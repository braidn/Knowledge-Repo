* where stubs are generated methods, mocks also know which methods should be called and what canned response should be returned.
* all of this is very meta but quite handy.
* 4 different libraries
  1. FlexMock: oldest and less commonly used
  1. Mocha: Used by Rails Core team
  1. Double Ruby: New kid on the block ( Mon, 09 Apr 2012 13:56:27 )
  1. Rspec: Built in mocking library
* Easily used in Rails by adding require 'mocha' to your test_helper.rb file. 
* Allows us to test the process along with the result
  * This is unlike normal testing that only cares about the end result
* Attempt to limit the amount of mocks in each test down to the lowest possible.
* Known for creating false positives, be careful not to rid testing suite with false positives

###Stubs

* A replacement for all or sometimes a part of a Ruby object.
* Hashed arguments correspond to the methods that the stubbed object returns
* Since the basis of Stubs is creating dummy objects, it is possible to stub both classes and methods.
* Returning different values is done with the `with` method
  * `Project.stubs(:find).with(1).returns(Project.new(:name => "Some project name"))`
  * The above could be used with an `assert_equal("Some project name", Project.find(1).name)`

###Mocks

* Really the same as a stub but demanding that all defined methods be tested during the duration of the specific test
  * Really diva like stubs...demanding you do EVERYTHING with them.
* Uses the `expects` method instead of the `stubs` method when dealing with creation