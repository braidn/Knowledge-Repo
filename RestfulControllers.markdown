You have seven default actions, and in every one of them you do the following:

* Set an instance variable to be used later in the rendered action or template
* Handle the response using the respond_to method to either do a render or redirect_to another path, depending on the behavior you want to achieve
* When rendering a partial or temp from another controller use: `<%= render :file => 'controllerName/tempName' %>`