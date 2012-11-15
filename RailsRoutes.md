* In rails the URL is related to the specific resource being requested.
  * In this way, URL begin to become the interface of the application.
* Since they are decoupled they can be modified to be meaningful
* Rails and RepresentativeStateTransfer are like [peanut butter and chinese food][1]
* Everything in `routes.rb` is compiled from top to bottom, meaning items at the top take priority.
* [Rails API routing][2] documentation
* Using `rake routes` in the app directory will show ALL available routes.
* Nesting is done in a block where all nested resources are placed in block. Still use resources :models naming method
  * This causes the parent to be the requirement (in urls/etc)
* {{RakeRoutesExamples}}
* If you only need several actions use :only => [:update, :destroy] or :except options
* {{RailsCustomRoutingActions}}
* {{RailsNestedRoutes}}

[1]: http://youtu.be/8RUO-V9BSnc
[2]: http://api.rubyonrails.org/classes/Actioncontroller/Routing.html