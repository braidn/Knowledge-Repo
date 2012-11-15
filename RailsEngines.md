* A slim subset of controllers, models, and views that are easily mountable in any Rails app
* Everything is easily overrideable
  * Rails first looks for things in the current app before looking in engines, gems, etc
  * this means if you name something in your app identical to that in a engine, it will default to your version over the engine
  * the spirit of duck typing.