#Redux Saga

##Notes

* Composable watchers that respond to events.
* Can be thought of as mini async processes when an event type is dispatched.
* Generators are used under the hood and are not supported natively in browsers
* Each operation is known as an 'Effect'.
  * In theory these should be easily testable without DI or mocks.

###Ease of Testing

* Because the workflow with sagas looks like:
  * call generator -> assert the desired effect -> return rake result
  * they are super easy to test.

##WTF Is a Saga?

* Sagas are process managers for dealing with complex workflows [created by: Hector Garcia-Molina and Kenneth Salem][1]

[1]: http://www.cs.cornell.edu/andru/cs711/2002fa/reading/sagas.pdf
