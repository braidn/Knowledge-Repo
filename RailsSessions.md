* `rake db:sessions:create` is used to generate the proper RailsMigrations vs the old standard `rails g` way
  * To complete the circle run over to config/initializers/session_store.rb and un-comment the last line
* The {{RailsFlash}} and session interface of rails is identical
  * Some EX: `session[:account_id] = @account_id` or `session['message'] = 'Hello World'`
* From here simply build a controller that lets the user login(new) and logout(destroy)
* When defining resources for RailsRoutes make sure you call resource != resources ( RailsResourceVsResources )
* It is often good practice to mod the the new(`new_session_path`) and destroy(`session_path`) paths to:
  * `login_path` and `logout_path` by passing `match '/login' => "sessions#new", :as => "login"`
* Session keys are defined as a 32-hex character key otherwise known as the `:session_id`
* A strict 4kb limit is global for all rails cookies
  * This leads to most cookies containing the "cart_id" for example over everything actually in the cart
* ALL volatile data should be kept in the database