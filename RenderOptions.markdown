* A blank call to render (`render`) will render an index.html from the corresponding view directory
  * This is also the default response to a method if render is undefined
* `render(:text => 'Some string')` is pretty self explanatory
* `render(:action => :index)`
  * This can be confusing, it renders the template ONLY, no action.
* `render(:nothing => true)` passes an empty body back to the browser
* All render forms take optional :status, :layout, and :content_type params
* {{RenderData}} to the user