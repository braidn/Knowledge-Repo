##notes

* Just a collection of models
* Acts a whole lot like [ActiveRecord][1] in rails
* Create from Backbone.Collections.extend
* Convention being that these are plural, where [models][2] are singular
	* Ex: `Albums` vs `Album`
* Simplest collections have `model: modelName ` and `url: "restUrl" ` attributes
* [Underscore methods][3] are used on the collection once it is created
* Events that collections fire: `add`, `remove`, `reset`
* [Collections View][4]

[1]: ActiveRecord
[2]: BackboneJs_models
[3]: http://underscorejs.org/#collections
[4]: BackboneJs_views
