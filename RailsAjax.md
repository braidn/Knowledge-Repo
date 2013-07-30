##Notes

* When adding actions to buttons call `remote: true` as a parameter
	* This could be done with link_to and using the :method modifier
* each file will adhere to a controller action and have a .js.erb extension
  * aka create.js.erb
	* these files house the response from the ajax request(replace html/move stuff)
* in rails 3.1 every js.erb file is playing favorites with jQuery.

###Request


###Response

* Use the `<%=j %>` helper to assist in making ruby code into a javascript format
* Pass back instance variables for use in the js.erb templates in the format.js call
	* ex: `format.js { @itemForJs = @InstanceVarSetinController }`
