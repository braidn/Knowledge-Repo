##Notes

* Building Sinatra apps in a modular fashion is more suited for complex apps
* Modular apps call `require 'sinatra/base'` instead of just `sinatra`
* This also aids when working in teams, each person can take on a small bit of functionality
* Each piece of the application turns into a class that inherets from `Sinatra::Base`
	* In each of these classes you can use sets, route handlers, and helpers just like a [classic app][1]
	* When finishing these class definitions, pass `run!` to start the app (explicit activation)
* When dealing with extensions in modular apps, they need to be explicitely registered
	* This explicit, granular registering gives us fine grain control over which modules are needed
* When calling PUT and DELETE we use a hidden field with a `_method` name
* This functionality is off by default in modular apps, turn on with: `enable :method_overide`
* Helper methods need to be explicitely called in each class that requires them
* Because we are just defining classes, we can inheret everything from a class
	* Routes, method definitions, and registers would be what gets inhereted
	* These could be easily overwritten in the new class if needed
	* An `ApplicationControlleler` is often the parent classed used for this type of inheretance

###Routing

* Use rack routing to route base urls `/admin/1` or `/songs/1` to their correct class
	* within the admin or songs class these routes would be difined as: `/:id`
* This type of namespacing is done in the `config.ru` file
	* use `map('/baseNameofUrl') { run baseNameControllerClass }`
	* this will also absolve us from calling `!run` at the end of the class definitions

###Setup

1. Build a class and inheret from `Sinatra::Base`
1. Register extensions (flash, auth) with `register Sinatra::Auth`
1. Before blocks are the same and nothing gets modified
1. Because helper blocks are actually class methods, you can remove the helper block and just
port the method definitions into the newly created class
1. Any database configure blocks go in the class as well
1. All routes stay the same and can be directly ported into the class

[1]: /Sinatra
