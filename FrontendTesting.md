##Notes

* There are many packages out there, all that mirror TDD/BDD style testing.
* Great place to start is to make sure that object containers exist.

###Methodologies/Ideas

* Many of the libraries that will be used throughout the application development
lifecycle are heavily tested. Make sure not to test these methods due to simple duplication.
* Due to the complexity of Frontend apps, sometimes strict TDD doesn't make sense.
  * this colides with the idea that your tests should lead or dictate your structure.
  * sometimes you need to spitball an implementation, catch up with tests and move on from there.
* Test should be more focused that the interface to these methods are called, not results.

###Tooling

* [Mocha][1]: Library that allows you to write describe/it style testing blocks.
* [Sinon][2]: Mocking/Stubbing/Spy library.
* [Chai][1]: Assertion library that allows you to actually test objects.

[1]: '/MochaJs'
[2]: '/SinonJs'