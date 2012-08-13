###Notes

* Stuff looks like they are below 3.2 which is weird, assets still sit in the assets folder in rails root
* View code written with HAML
* 1 action will deal with the retrieval of the form while the 2nd action will submit it.
* Create works with the POST action and edit works with PUT (this will likely change with 4.0)
* In controllers, instance variables persist for only one request
* Fat views are a good window into the PHP developer
* SOA stands for Service Oriented Architecture (basically APIs)
* PLEASE put a lot of the code into the models
* TDD will lower the amount of debugging needed.

###Trip Through a Rails App Request

1. Routes map incoming URLs to controller action and extract any optional params
1. Controller actions set instance variables to be usable with the views. All of these get smashed away in `params[]`
1. Controller action eventually render the view

###Rails Philosophy

* Convention over configuration: In Rails this really means naming follows certain conventions, therefore no need for config files
* DRY <- we know this, Don't Repeat Yourself

###Database

* Rails offers 3 separate environments that correlate to a different database for each (dev, test, production)
* Migrations change database but are really just simple scripts that describe the changes needed for the database
* Migrations are sweet because they are reversible, and version controllable, AND awesome, AND reliable/automatable
* Migrations are created through `rails g migration migrationName`
* Migration table is held around so it knows when new and already run migrations are sitting around
* Life really begins at the creation or the modification of Models/Migrations in a rails app.
* Rails builds SQL queries at runtime based on the Ruby code
* Database table column names are getters and setters for model attributes
* Bangs(!) throw exceptions back to the user or collectable by the app, and regular methods throw nil and forget about it.

###Reading Things from DB

* `where` class method where selects objects based on attributes
* the database wont be flooded with searches, it works when all wheres are finished "loading"
* [dynamic attribute finders][1] are also great for finding specific stuff

###Updating Things from DB

* `update_attributes` will take a hash and modify everything in the specific db
* If any of the attribute mods change nothing will be changed (aka the DB is transactional)

###Deleting Things from DB

* `destroy` is handy because it will destroy all associations
* all objects that are assigned to a var, or in memory are accesible but not modifiable (getter works/setters don't)

###Controllers and Views

* To add a Controller, their needs to be a route, an action in the controller, and an item for something to render (html.haml file)
* Think hard about what else the user can do and how the user will get to the specific action
* Don't forget the awesome helper methods provided by routes

###Debugging

* STDERR is generally useless and hard to localize
* RASP (Read, Ask, Search, Post) is a great way to debug an error
* __Always__ remember that Ruby is a bunch of files, search through the full stack of errors.
* Use the keyword `debugger` where the app is having a fit and when the app is loaded, it will drop you into the state of the app where the bug hit.

###Forms

* Forms are associated with creating a new record into the DB
* Usually we work with a `New` and `Create` action
* General strategy: Identify the action that gets the form itself and what receives the submission
* Make sure to think about the `action` and `method` attributes that are passed with the form tag
* URI helpers can be used to for `action` although we still need the method (snippets will generate this nicely btw...)

###Redirection, Flash and the Session

* Use the keyword `continue` to snap the debugger back into action
* Mission would be to redirect the user page to something useful depending on the success rate
* Redirect triggers a whole new HTTP request (loss of state occurs during this)
* Flash hash is used to notify user in the next request of a success or fail. Goes away afterward.
* Session hash persists forever or until it is wiped
* Default storage mode for Flash and Sessions is browser cookies
* Alternative to cookies is a DB table or NoSQL storage system like memcached
* Session hash is used a lot when it comes to authentication purposes
* Cookies have a size limit of 4kb so the potential of this limit being hit is very likely
 

[1]: http://api.rubyonrails.org/classes/ActiveRecord/FinderMethods.html