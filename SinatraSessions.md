Need to be activated by passing `enable :sessions` in the `configure do` block

* Use session[:hashKey] to initiate a session
  * A really easy way is to set the key to `#{Time.now}`
* To __Destroy__ a session send a call to `session.clear` for a specific URL. Once the user has hit the URl, the session will clear
* When dealing with session data it is bessed to use Sinatra's `halt(errorCode, Message)`
	* example: `halt(401, 'Not Authorized'), unless session[:something]`
* Sessions are unstable so look into sinatra-authentication or warden gems
* [A Sinatra sessions example](/SinatraSessionExample)
