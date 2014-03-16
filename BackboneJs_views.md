##Notes

* uses a `render()` function to push an `el` tag (this can be changed with
  * very common to just create a render function when creating the view
`tagName:`) to the DOM
* templates are done with underscore library (default)
* Views themselves are responsible for responding to user interaction
  * this is done by calling `events: {}`
  * and passing in `"<event> <selector>: <function>"`
  * below the events attribute we define the function `<functionName> : function(){do something;}`
	
###Collections

* Will extend from the all ready defined view (instead of backbone)
* Offten times have the word list in them (PlayerListView)
	* This is a formality designed from building desktop applications

###Events / Event Handlers

* Events (button clicks) are placed into their corresponding view/collectionView
	* syntax is `events: { 'eventName cssName': 'functionName' }`
* jQuery events are a good place to start
* Elements can be anything (button, div, etc)
* Methods are defined in the current view.
