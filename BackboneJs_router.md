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
* Often times the app instance is a new Backbone.Router.
  * This instance is initialized at the end of the file in a jQuery anon function.
  * Afterwards you would call `Backbone.history.start({pushState: true})` to start.

###Routes

* The empty route or `''` refers to the root of the website

###Antipaterns

* Not really meant to be a grand orchestrator. Back button will fire whole App changes.