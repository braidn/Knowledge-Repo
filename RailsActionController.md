# Rails Controllers

##Notes

>Instructions on how your app will handle certain requests(called methods or 'actions'). Some things to think about:  

* Unless otherwise declared, all methods in a controller class are public.
* Usually when actions complete their work they respond by rendering a view by using a RespondToBlock
  * The controller responds to the user exactly once per request.
	* ex: `respond_to do |format| end`
	* This means that you could not have two `render()` methods per request
* use the keyword `return` to jump early out of a resource
* If in the controller and you pass `respond_to` an item not surrounded by {} then it looks for it's name (create, delete, show) in the proper view directory.
* If you place a `private` method in the application controller it will be accessible by ALL controllers BUT never as an action
* If your model differs from the class of the controller, this can be changed:
  * ex: `def model_class; ::SomeClass; end`
  * the `model_class` method will overide the rails magic of constant lookup.

## Testing

* As of Rails5, controller tests are now slower than integration tests.
  * When testing iVars now, we should use the `instance_variable_get` method over `assigns()`

### Other Resources

* [RestfulControllers][1]
* [RailsFilters][2]
* [RenderOptions][3]
* [RenderToOptions][4]
* [RailsControllerScrathPad][5]

[1]: /RestfulControllers
[2]: /RailsFilters
[3]: /RenderOptions
[4]: /RenderToOptions
[5]: /RailsControllerScrathPad
