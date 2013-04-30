##Notes

* To get started, make a class and have it inheret from `Sinatra::Base`
* A simple `configure` block will set up the needed items (views, etc)
* Require the middleware like any other file
	* and call `use middlewareClassName` in the needed classes
* Since all of these are class methods we could call `ClassName.disable :something`
	* Instead of changing it directly in the Middleware class
