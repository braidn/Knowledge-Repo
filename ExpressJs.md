# Express

## Notes

* npm start looks for server.js not the prebuilt app.js
	* node defaults are actually server.js
* Express is open ended when it comes to file/folder layout, do what you want
* [Jade][1] is the default template engine for Express
* `npm install library --save` will add lib to the current dir and add lib to package.json
	* if anything is wrong with package.json the error will fail silently and nothing will be written
* Like Rails, express utelizes a session flash to persist info on next request
* Response handles redirection and rendering
* The Request deals with sessions mostly
* Express is fairly open so to better segment code, create an `apps/` dir
	* In the directory we can create a myriad of _little apps_ to keep code separate
* `req` item handles flash and session items
* `res` item handles rendering and redirect items

## Params

* Preprocessing can be done on all parameters using a concept called 'route params'
* Great place to do validation/database fetches.

## Routes

* Url handling is key and with express you need to instantiate each url/route
	* This is very much like how [Sinatra][2] handles itself

[1]: http://jade-lang.com/
[2]: /Sinatra
