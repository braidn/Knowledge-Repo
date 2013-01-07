##Notes

* Most apps will have more than one.
* They are named due to their functionality
	* `AdminRoutr`, `UserRouter`, etc
* Like most things, extend `Backbone.Router` to _get started_
* Contains:
	1. `routes:` which is a hash of `url: functionToHandleUrl`
	1. `initialize:` used to set everything up
	1. `custom functions:` that are being used by the hash syntax under routes
* Often times the app instance is a new Backbone.Router
	* This instance is initialized at the end of the file in a jQuery anon function
	* Afterwards you would call `Backbone.history.start({pushState: true})` to start

###Routes

* The empty route or `''` refers to the root of the website
