1. Rails receives a request from the outside world (usually a browser).
2. Routing picks apart the request to determine the controller and action to invoke.
3. A new controller object is instantiated, and an action method is called.
4. The controller interacts with the model (usually performing a CRUD operation).
5. A response is sent back to the browser, in the form of either a render or a redirect.