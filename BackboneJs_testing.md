## Notes

* When starting an application it is best to devise a test plan.
  * This is really due to the fact that TDD may not be the best plan in a FrontEnd app.
  * These can be either simple sketches or multi page, drudge reports that require sign off.
  * Sometimes Wiki's make for good test plans as well.

### Testing Methods

* _Unit Test_: Testing a model is created and morphed correctly.
* _Partial Integration Test_: Testing that a view/subviews are constructed properly and that collection changes properly change the views.
* _Regression Tests_: A bug is defined and test verifies bug, with code fixing it.

### Testing Models

* Objects can be instantiated with defaults.
* Data can be correctly synced with DataStore.
* Custom events fire correctly and change state appropriately.
* Validation logic in fact works and changes model state.

### Testing Collections