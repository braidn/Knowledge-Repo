##Notes

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
