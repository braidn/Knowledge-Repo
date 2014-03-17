###Getting started 

* download the sinatra gem, require 'sinatra' in the .rb file and to get it running locally use ruby fileName in terminal.
* use a config.ru file for working with Thin
  * you can pass `#\ -thin flags` at the top of the file to set items like the port

###General

* [Sinatra Routes][1]
* two approaches to building web stuff with Sinatra
  * modular mode: explicitly subclass sinatra and build within the scope
  * classic mode: require sinatra and start building out endpoints 
* use `require 'rack/test'` if you are using rspec/capybara.
  * In many cases you need to also define a new method called app and in the body include `Sinatra::Application`
    * This is common in many Sinatra apps
    * Also known as modular mode
  * In every describe that requires Sinatra make sure to `include Rack::Test::Modules` to access get/post methods
  * `set :environment, :test` after the requires to make sure rspec knows Sinatra is in dev/test mode
* Layout file used to build a cross app template.(template engine can be HAML, erb, etc)
	* this file or inline name is always `layout`
	* like rails, use `yield` keyword to place info from templates into layout
	* additional layoutes can be created by calling `:layout => :name` for the correct route
* Public folder (assets) by default is named `public` and views is `views` <= convention!
	* if for some reason you want to change, call `set :public_folder, 'newName'` and `set :views, newName`

###Ajax

* Sinatra responds to ajax calls using `.xhr?` method
* When returning templates this way it is best to return without a layout
	* this ensures that the html will be slotted into the correct tag and the layout wont be duplicated

###Helpers

* Defined much like environments: `helpers do end` block
* Any method defined in this block can be used within _route handlers_ and _views_
* Helpers can also be defined by creating a module and calling `helpers moduleName`
* Helpers allow us to keep route handlers short and descriptive, which is what we want

###Before Filters

* Placed after configuration files at the top of app.rb
* Run before each request is fulfilled
* Many times they are used to invoke setup that will be required by each request

###Sinatra Environments

* These environments are set up in configure /do blocks
	* example: `configure :production do`
* Settings are fiddled with using the global `set :views/static/public_folder` syntax
	* these can be accessed by calling `settings.views/static/public_folder`

[1]: /SinatraRoutes
