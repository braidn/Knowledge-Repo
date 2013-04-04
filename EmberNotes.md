##Scratch

* Calling `reopen` on something acts very much like monkey patching in rails
* Fixture data can be a great way to build out the clients side without dealing with data/servers
* Computed property: functions built onto models
	* the end of the function must be: `}.property('')`

###Controllers

* Provides 3 diff controllers: Array, Object and "Controller"
* All controllers are generated at start
	* As long as the viewport is active, controllers stay instantiated
* One page could have many controllers working at once

###Routes

* ApplicationRoute is the special route for the ember app itself

###Templates

* When dealing with attributes use `{{ bindattr attrName = 'modelItem' }}`
* Within an `{{#each}}` you can define an `{{else}}` that will act if `array.empty? == true`
* Blank state items with actions required is generally considered good UI design

###Debugging

* None minified version of ember.js has error messages
	* use the minified version when in production mode
* Use the `debugger;` statement to have the app halt at a certain point in the code
* To find what controller you are looking for use `{{ controller }}` in the view
	* this also works with models ( `{{ model }}`)

###Helpers

* Kind of conveluted, called by defining a Handlebars helper:
 * `Ember.Handlebars.registerBoundHelper('name', function(){});`

###Actions

* Clickable items that don't modify the URL
* Is written like: `{{ action "someFunctionName" someArg }}`
* Functions get placed in the controller where the action is needed
