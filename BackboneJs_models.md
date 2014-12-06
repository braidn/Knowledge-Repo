##Notes

* Think of class definition when working with AR
* `defaults:` is a key/value set that adds properties to each
newly initiated model
* use `get` and `set` methods so proper watchers will be fired
* A model will often have a bunch of methods
* models are often built prior to a interface so they can be tricky

##Methods

* `Parse`: Run once the model from the server is returned. Great for overriding data.
  * working with nested data you can parse out and re-manage items.
* `toJSON`: Create a json representation of the model data.

##Attributes

* Accessed with the above `get` and `set` methods.

##Events

* `this.on()` is one way, maybe not the best way to listen to events

##Persistence 

* Items are saved with the `save()` method to the server
* Items are deleted with the `delete()` method from the server
  * references to the model will not be destroyed though.

##REST

* Really works with the URL and the method name (GET/POST)
  * example: `GET /users/1 data: { first_name: 'wicked' }`