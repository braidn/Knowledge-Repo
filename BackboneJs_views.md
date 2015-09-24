##Notes

* More traditionally the 'Controller' in MVC
* Manage the presentation of a mode
* uses a `render()` function to push an `el` tag 
  * this can be changed with `tagName:` to the DOM
  * very common to just create a render function when creating the view
  * ex: `$(this.el).html('<h1>I am big</h1>')`
* templates are done with underscore library (default)
* Views themselves are responsible for responding to user interaction
  * this is done by calling `events: {}`
  * and passing in `"<event> <selector>" : "<function>"`
  * below the events attribute we define the function `<functionName> : function(){do something;}`
* Views can be created to encapsulate existing elements on the page.
  * this is interesting because you can capture events not defined elsewhere.
  * creates a scoped jquery selector to the domNode, not the document root.
  * this can be thought of as a mini application or perhaps a component

###Rendering

* The actual render method is a noOp on all views. This forces us to define it
* Able to change the view by key value pairs: `tagName: 'li' / className: 'bilbo'` 
* Allows the dev to use an element that exists on the page.
  * do need to wait for the document to be ready before having access.
* Rendered views can be removed by calling `remove`.
* Sometimes best to organize an app around a single view/entry-point.

###Templates

* HTML fragment that accepts a JS object that fills in the interpreted sections.
* Should not be used in script tags if in Production.
  * precompilation can be done during the deploy process and won't slow down a user later.

###Events / Event Handlers

* Events (button clicks) are placed into their corresponding view/collectionView.
	* syntax is `events: { 'eventName cssName': 'functionName' }`
* jQuery events system.
* Elements can be anything (button, div, etc).
* FuncMethods are defined in the current view.
* Memory Management:
  * use `this.listenTo` to listen to events and it will remove object references as needed

###CollectionsViews

* Will extend from the all ready defined view (instead of backbone)
* Offten times have the word list in them (PlayerListView)
	* This is a formality designed from building desktop applications
  * 

### Common and Cryptic Errors

* `this._ensureElement is not a function`
  * the new keyword wasn't used to instantiate this view.