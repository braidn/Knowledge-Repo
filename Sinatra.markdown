Getting started: download the sinatra gem, require 'sinatra' in the .rb file and to get it running locally use ruby fileName in terminal.

* {{SinatraRoutes}}
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