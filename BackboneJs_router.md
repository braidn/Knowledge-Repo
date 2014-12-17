##Notes

* Most apps will have more than one.
* Supports both the hashbang and the HTML5 History API.
* They are named due to their functionality.
  * `AdminRoutr`, `UserRouter`, etc.
* Like most things, extend `Backbone.Router` to _get started_
* Contains:
  1. `routes:` which is a hash of `url: functionToHandleUrl`.
  1. `initialize:` used to set everything up.
  1. `custom functions:` that are being used by the hash syntax under routes.
* Each route in the route table will map to a function (1to1).
* Regexes are completely ok in the routes table.
* Routes are matched from top to bottom which leads to order mattering
  * an example of this would be: `routerInstance.on(route:SomeFunction, function() { do_stuff })`
* Often times the app instance is a new Backbone.Router.
  * This instance is initialized at the end of the file in a jQuery anon function.
  * Afterwards you would call `Backbone.history.start({pushState: true})` to start.

###Routes

* The empty route or `''` refers to the root of the website
* `*other: "defaultRoute"` is a good method to get into to catch all non catched routes
  * users are known for their random URLs
* Regular expression routes should be setup in the `initialize` method
  * using `this.route(regex, method)`
* Routes can listenTo or fire on specific events. These events can be actual route names

###Antipaterns

* Not really meant to be a grand orchestrator. Back button will fire whole App changes.
