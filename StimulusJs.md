# Stimulus Framework

## Notes

* JS framework that was pulled from Basecamp3.
* Hinges heavily on Controllers.
  * This makes it feel a lot like Angular 1.6 lite.
* Obviously integrates really well with your existing code.
  * Feels very much like Backbone.js did back in the day (sprinkles of JS).
* Controllers can load user specific fragments leaving base HTML easy to cache and small.

## Controllers

* Instance of JS classes whose methods act like event handlers.
* Act just like controllers should. They are communication between the DOM and JS logic.
* Connected to the dom through data attributes
  * ex: `data-controller="hello_world"`
* Once this data attribute is found in the DOM, Stimulus creates an instance of the specific Controller.
* Can have custom methods that map to Action Descriptors that get fired from the DOM.
* Because these end up being instances of classes, multiple can be active per page.
  * meaning we can heavily reuse controllers in different blocks of the DOM.

## Controller Methods

* `connect()`: Fired every time Stimulus connects a controller to the DOM.
* `disconnect()`: Fired every time the controller disconnects from the DOM.
* `initialize()`: Fired once when the controller is instantiated.

## Action Descriptors

* Any data action that maps back to a custom method on the controller.
* Args: The event that's passed in (`event`).
* ex: `data-action="click->hello#create"`
  * the first part is the event type (click, input)
  * second part is the controller name and method (hello: controller, create: method)
* Stimulus does have some shorthand handlers for certain DOM elements.
  * ex: `a` or `button` maps automatically to `click`
  * This omits the need for the `click->` part of the data attribute

## Target Descriptors

* Marked DOM elements that are referenced in the controller code.
* Often used to get data into the controller from the DOM.
* ex: `data-target="hello.name"`
  * The first part of the target is the name of the controller.
  * The second part is the target name.
* Controllers must retain a list of all targets that are used.
  * ex: `static targets = ["name", "location"]`
  * the example targets would be availble under: `this.nameTarget` and `this.locationTarget`
* For each target listed in the array, Stimulus creates 3 methods on the class:
  * `this.nameTarget`: evals to the first name target in scope or throws an error.
  * `this.nameTargets`: evals to an array of all name targets in scope.
  * `this.hasNameTarget`: evals to a boolean if there is a name target. False if not.
## Data API

* Convenient methods to get at data attributes scoped to the controller.
* `this.data.get(name)`: returns the string value bound to the name data attribute: `data-controllername-data='somedata'`.
* `this.data.has(name)`: returns a boolean if the data exists.
* `this.data.set(name, newVal)`: sets the new value of the data attribute.
* Multiple word data attributes (ie: `data-controller-my-name`) is transformed to:
  * `this.data.get("myName")` camelCase in the controller
