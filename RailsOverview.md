	* `after: :email` place it after another column
	* `limit: 30` limit the size
	* `unique: false` unique not needed
* `Remove<Anything>From<TableNamePlural> column:type` will remove the column
	* Once run you should dive in there and create a down method for rollback sanity
* Foreign keys are easily created by adding a `add_index :currentModel, foreignKeyModel_id`
	* On the foreignKeyModel it needs to be singular

###Models

* Use _scopes_ to define chainable sql clauses (what it sounds like)
	* syntax: `scope :scopeName, where('Something')`
* _Callbacks_ are basically `before_action` and `after_action` calls to methods
* The idea: before saving this model fire this method: easy
	* __IF__ these methods return false, the save stops
	* There are a myriad of callbacks, check them out
* For relationships between models, there are a ton of options... :use => api
* When dealing with join tables and :through make sure:
	* both id's are created on the join as well as both indexed
	* __NO__ added foreign keys are needed in the other migrations, _just_ the join table
	* Still have to call the `has_many` on the join table for both related tables
		* this means that the join table gets `belongs_to`
	* The other `has_many` will read `has_many OtherTable(plural), through: :joinTable`
	* If an instance calls the has_many :through name it will magically do a Join

###Controllers

* The `includes(:modelNamePlural).all` will prefetch the association and save on query time
	* This is something that should be APIed as well and is relationship based
* `put` and `delete` verbs were introduced in Rails 2
* Special routes or `member routes` are just ways to reference other methods in the controller

###Routes

* If you didn't want to use URL helpers:
	* use `link_to linkTitle, modelName, method: :methodName` 
	* the methodName could be `:put, :delete, :post`
* When using the show helper you can omit it for just write the instance `@bills, @cubes`
* The helper methods can be called as `bill_path` (relative) or `bill_url`(absolute)
* When working with _nested routes_:
	* make sure to change up your controllers to deal with the extra id's passed in params
	* this may cause you to instantiate an instance variable from one id
	* and pass it into the second instantiation of the final instance variable...
	* this would look like in a bills controller:
		* `@lender = Lender.find(params[:lender_id])`
		* then: `@bills = @lender.bills.find(params[:id])`
		* kinda convoluted, but very powerful
	* rake routes will give you an idea of what id's are being passed into the URL/URI
	* when using show, or delete you can pass these id's as an array in their proper order
	* and in your forms, the array will be passed in the `form_for([@model1,@model2])` section
	* in addition, you will need to change your `respond_to` blocks in your controllers
* When creating custom routes or `member routes` follow:
	* the syntax to do it in routes.rb is: `get :methodName, on: :member`
	* sorta cryptic but it produces `methodName_modelName`, the url, and sets the action and controller
	* a `:member` route will return a single resource (bills/id/customRoute)
	* and a `:collection` route will return a collection of resources (bills/customRoute)
	* each custom route needs to be described in this way

###Forms

* Rails hands off some great helpers:
	* `form_for(@modelName) do |f|` to create a form for :put or :create
	* in the form_for you have `.label :columnName` and `.text_field :columnName` along with other fields
	* and the `.submit` will create a button to submit to :put or :create
	* `.radio_buttons` are normally listed out, each one
	* `.select` boxes can be accompanied with an array of selectable values
* Some additional (read: special) input fields include:
	* `.password_field` for obscuring input
	* `.number_field` for numbers only
	* `.range_field` for the slider of choice
	* `.email_field`, `url_field`, and `.telephone_field` will hand off the correct mobile kb

###Partials

* Any view item that begins with an underscore. In many cases this will be the form
* When using render, we can trick rails into doing things for us:
	* on index we call render @items then it will build a loop for us
	* the singular of the @items will be item
	* and all the html can be pushed into the partial itself
	* This is "clever code" though, so be careful

###Rendering

* If you want more than html to render you need the `respond_to do |format|` block
	* __IF__ rendering html, just call `format.html` (this will render the file with the name of the action)
	* __IF__ you wanted to render a different bit of html, pass `format.html { render :name }`
	* these `format.html` blocks can be broken into by using do/end and logic added
	* within here there will be `format.responseType { render: @object }` call
* If we only care about JSON (API) then we can just call `render json: @objectName`

###AJAX

* Start by restructuring links to include: `remote: true` at the end of the `link_to` tag
	* This generates an HTML5 data attribute with the name `data-remote = true`
* Jump into the controller, find the action, and in the `respond_to` block add `format_js`
	* Add the corresponding Js to the correct manifest file (this will be named after the controller action).
* To use Ajax with forms, just pass `remote: true` into the `form_for` declaration:
	* An example would be `form_for(@bills, remote: true) do |f|`
* All of these js.erb files will live in `app/views`
	* This might mean you have a `index.html.erb` as well as a `index.js.erb`
	* the html part will live in the html file and how the AJAX will work lives in the Js file
	* Much of what will be in the js.erb file will be `.show()`, `.hide()` stuff
	* Since these files are .erb based there can be plenty of ruby as well.
	* jQuery can be used and usually is quite liberally within the js.erb files

###Helpers

* `div_for` blocks are handy for presentation html with correct id's and classes
* many helpers can be found in ActiveSupport documentation
* Arrays can be called with `.to_sentence` to create a list for a sentence (handy)

###Mailers

* Like with most things, rails can generate mailers using: `rails g mailer MailerName methods`
	* the methods are optional
	* the mailers that are created, by default are text based, this can be solved by changing them to html
* The email is actually sent by defining and calling the private method in the model
	* in many cases a specific instance variable will be sent into the mailer...
	* this can be performed by passing `self` as the param in the model method
* To send we call: `MailerName.methodName(paramsNeeded).deliver`
	* pass the method call into a callback and BOOM! Email like a boss
	* and it is best to do it, only if the method has changed, or better yet? on :post

###Assets

* The pipeline is pretty sweet and pushes everything into `/assets/*.*` url
* Every file is cached by adding a hash to its name
* To access hashed versions of assets in a stylesheet:
	* end the file with .erb...
	* pass `<%= asset_path('assetName')%>` and BOOM!, the reference will be the cached file
* To require the files in `/lib` and `/shared` just include them in the sprockets manifest (Js)
	* To include CSS, put it in lib or shared and use application.css.scss to include it
	* If an `include self` shows up it is referencing the file that is open

###JSON

* Make sure to send the correct HTTP status codes when needed.
	* This would be done by calling `status: :some_status`
* When responding with a resource, make sure to use the `location:` option as well
* When responding to json:
	* call the instance object within render: `render json: @someInstance`
	* if you only want to return some of the json attributes: `to_json(only: :item)`
	* so if you wanted to see the cost of your bill: `@bill.to_json(only: :cost)`
	* if you want more, pass an array of items to the `only:`
	* if you want to omit everything except use the `except:` instead of `only:`
	* if you want to omit many fields, just pass an array after `except:` or `only:`
	* if you have a relationship, call `include: :modelRelationShipName, only: :awesome`
