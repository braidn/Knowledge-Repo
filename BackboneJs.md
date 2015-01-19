## Reasons to use Philosophy.

* Avoids tying the application to the state of the dom.
* Adds the idea of file organization, although this is very open.
* Makes life testable. (Developer Ergonomics)

## Notes

* Basics are fairly simple:
  1. Set up a model to hold all the data
  1. Set up a view to output the information to the browser
  1. Instantiate an instance of the model class
  1. Instantiate an instance of the view class and pass the model
     instance in
  1. Do some cool shit
  1. Save, said cool shit

## MVC Pattern

* Models and Views are fairly similar to the classical idea of MVC
* Controllers are where almost all JS frameworks differ from stuff like Rails
  * Instead of considering Backbone to be MVC, think MV*
  * The idea of controllers is split between `Backbone.View` and `Backbone.Router`
  * Models/Collections are really just ways to persist the data to a backend of sorts.

## External Pages

* [Views][1]
* [Models][2]
* [Collections][3]
* [Router][4]
* [[Backbone Antipatterns|BackboneJs_antipatterns]]

[1]: BackboneJs_views
[2]: BackboneJs_models
[3]: BackboneJs_collections
[4]: BackboneJs_router