##Notes

* uses a `render()` function to push an `el` tag (this can be changed with
`tagName:`) to the DOM
* templates are done with underscore library
* Views themselves are responsible for responding to user interaction
  * this is done by calling `events: {}`
  * and passing in `"<event> <selector>: <function>"`
  * below the events attribute we define the function `<functionName> : function(){do something;}`
	
###Collections

* Will extend from the all ready defined view (instead of backbone)
