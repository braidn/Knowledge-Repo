Sinatra's main DSL is built off from simple _verb 'route' do_ blocks

* All of the blocks are read from a top-down hierarchy. This becomes important when using wildcard selectors
* Multiple urls with same behavior can be expressed as:

      ['/one', '/two', '/three'].each do |route|
      get route do
        "Triggered #{route} via GET"
       end
      post route do
        "Triggered #{route} via "POST"
       #And so on
      end
       end

* {{SinatraRouteParams}}
* Logic is passed into {{SinatraViews}} from each route.
* Provides a `not_found do` block to handle 404 issues that might arise.  
  * `error do` blocks are used to handle 500 errors.
* Headers can be changed in blocks by passing: `headers "nameOfHeader" => "headerContent"`
  * You can chain header morphing along with a simple "," between each header change.