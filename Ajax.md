# Ajax

[[toc]]

## Notes

* `load` is the most simple, it fetches data from the server and places it into 
the matched element
	* one can filter everything by passing a id/class to the argument in load
	* this is hackey but a way to control the flow coming back
* `post` will post items to the server
	* when using this often times a form is sent, use the `serialize` method to send 
	form data

### AjaxMethod

* `ajax` method is the lowest level method, all others work with this specifically
* `contentType:` tells the server what kind of data you are sending
* where `dataType:` tells you what kind of data the server is returning

### AjaxSetup

* Most are considered globabal "Ajax Event Handlers"
* Several methods can be used to fire events depending on ajax timing
* `ajaxStart` and `ajaxStop` do exactly what you would think
* `ajaxError` will fire when your ajax isn't working quite right
* Many of the variables like `dataType` can be set here

### JSONP

* A call from the client to the api is made along with specifying a specfic function
	* the server responds and keys and values within the function name specified
* jQuery has all that is required built in
	* just send `callback=?` as a special key into the url.
	* jQuery will than throw the response into the success function

### Rails

* When using `heads :ok` rails actually returns a json string containing a single space.
  *  This is not considered valid and will not allow a success block to fire when using jQuery.
