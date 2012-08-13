Instructions on how your app will handle certain requests(called methods or 'actions'). Some things to think about:  

* Unless otherwise declared, all methods in a controller class are public.
* Usually when actions complete their work they respond by rendering a view by using a RespondToBlock
  * The controller responds to the user exactly once per request.
    * This means that you could not have two `render()` methods per request
* use the keyword `return` to jump early out of a resource
* [RestfulControllers][1]
* [RailsFilters][2]
* If in the controller and you pass `respond_to` an item not surrounded by {} then it looks for it's name (create, delete, show) in the proper view directory.
* If you place a `private` method in the application controller it will be accessible by ALL controllers BUT never as an action
* [RenderOptions][3]
* [RenderToOptions][4]
* [RailsControllerScrathPad][5]

[1]: /RestfulControllers
[2]: /RailsFilters
[3]: /RenderOptions
[4]: /RenderToOptions
[5]: /RailsControllerScrathPad