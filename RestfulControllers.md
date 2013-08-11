##Notes

* You have seven default actions, and in every one of them you do the following:
	* Set an instance variable to be used later in the rendered action or template
	* Handle the response using the respond_to method to either do a render or redirect_to another path, depending on the behavior you want to achieve
	* When rendering a partial or temp from another controller use: `<%= render :file => 'controllerName/tempName' %>`
* `new` and `edit` are _actually_ not RESTFUL
	* these end up being different ways to represent the `show` action
	* this can be thought of while building an API, why build new over create
	* the big five(`index`, `show`, `create`, `update`, `destroy`) are what matter
