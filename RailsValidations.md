for a base understanding of R3 validations go here to the api

common ones include:

* `validates :email, :uniqueness => true`
* `validates :title, :presence => true`
* `validates :email, :uniqueness => true, :length => { :within => 5..50}`
* `validates :email, :format => {:with => /someregex/}`
  * The key to this is regexex. Learn them and love them
* `validates :password, :confirmation => true`
* {{RailsCustomValidations}}

The CSS class that is wrapped around the errors is called `fieldWithErrors`
Use this to style elements correctly. The original files are created when invoking the scaffold generator and are held in public/stylesheets/scaffold.css