## Notes

* When starting an application it is best to devise a test plan.
  * This is really due to the fact that TDD may not be the best plan in a FrontEnd app.
  * These can be either simple sketches or multi page, drudge reports that require sign off.
  * Sometimes Wiki's make for good test plans as well.


### Testing Methods

* _Unit Test_: Testing a model is created and morphed correctly.
* _Partial Integration Test_: Testing that a view/subviews are constructed properly and that collection changes properly change the views.
* _Regression Tests_: A bug is defined and test verifies bug, with code fixing it.

### What To Test?

#### Testing Models

* Objects can be instantiated with defaults.
* Data can be correctly synced with DataStore.
* Custom events fire correctly and change state appropriately.
* Validation logic in fact works and changes model state.

#### Testing Collections

* Since Collections rely on a model, this is ok to if stubbed.
* Collections can successfully be created with or without an array of model objects.
* Models can be added or removed from the collection.
* Data is appropriately synchronized between backend.

#### Testing Templates

* The appropriate HTML and Data is rendered.
* Data structures like Models and Collections are properly displayed.

#### Testing Views

* By far the most dependencies laden Backbone component:
  * This will lead to a lot of headache and dependency stubbing.
* Views can render to HTML, binding model data to a string.
* View properties with an `el` get bound properly to the DOM.
* Methods bind properly to Events and respond accordingly
* Objects contained by the view (subviews) are deposed of properly.

#### Testing Routers

* URL's are mapped to their Views or other actions.
* A Router maintains the browser history.