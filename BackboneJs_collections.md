##Notes

* Just a collection of models that are captured and managed.
* All models have a collection property to trace lineage.
* Models can have more than one model but the first one is canonical.
* Acts a whole lot like [ActiveRecord][1] in rails
* Create from Backbone.Collections.extend
* Convention being that these are plural, where [models][2] are singular
	* Ex: `Albums` vs `Album`
* Simplest collections have `model: modelName ` and `url: "restUrl" ` attributes
* [Underscore methods][3] are used on the collection once it is created
* Events that collections fire: `add`, `remove`, `reset`
* Has a URL very much like the model so things can be fetched from something RESTful
* [Collections View][4]

###Collection Methods

* Many of these are proxies to Underscore methods like map/filter.
* Most transformative processes are mapped 1to1 to Underscore
* `remove`: filter a collection into a variable and then remove all models from that.
  * will take one model or an array of models.
* `add`: add a specific model to the collection.
* `at`: pass it an index and it will return a single model.
* `pluck`: pull a single attribute from every model as an array.
###Extending Collections

* If extended, you get everything from the original but allow a parent/child subclass idea

[1]: ActiveRecord
[2]: BackboneJs_models
[3]: http://underscorejs.org/#collections
[4]: BackboneJs_views