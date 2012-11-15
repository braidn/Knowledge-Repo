###Routes File
~~~
root :to => "model#controllerName
~~~~

###Links

~~~
<%= link_to 'Home', root_path %>
~~~~

* `[:edit, @projects, @tickets]` is a short hand array that basically says: `edit_project_ticket_path(@project, @ticket)`
  * this alone makes rails routing very smart