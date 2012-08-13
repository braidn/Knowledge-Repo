###Index

* Cycle through all of the items which means our instance variable will need to be enumerable....aka a fat stack
  * fat stack == `@items = Item.all`
* lots of fat stacks...hur *drool*

###Show

* Show one specific item by creating an instance method: `@item = Item.find(params[:id])

###New

* Much like edit, builds a instance variable to use with the new.html.haml view
  * `@project = Project.new`
* we would want to render the _form partial in the view so we can fill things out

###Create

* Functions a lot like the update method. Gets it's information piped to it via the new view
* When creating the instance var make sure to call new on it: `@item = Item.new(params[:project])
* Then `if @project.save` then redirect to the new @project with a handy dandy message to the notice hash
  * If the project.save method fails then we should re `render :action => 'new'`

###Edit

* Used by the view to call on the update method.
* Help out the view by creating an instance method: `@item = Item.find(params[:id])`

###Update

* Find the item to be updated
  * @item = Item.find(params[:id])
* If `@item.update_attributes(params[:project])` is successful flash something to the notice hash
  * redirect them to their newly updated project
* if not flash something to the alert hash and `render :action => 'edit'` back to them

###Destroy

* Find the item by its id
  * `@item = Item.find_by(params[:id])`
* Call destroy on it
  * `@item.destroy`
* Flash to the :notice hash something that makes sense
* Redirect the user to the items_path(index)
  * `redirect_to items_path`