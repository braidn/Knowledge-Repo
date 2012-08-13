Responsible for dissecting the incoming url and delegating control to the appropriate controller and action. Otherwise known as "routing"

* In rails the URL is related to the specific resource being requested.
  * In this way, URL begin to become the interface of the application.
* Since they are decoupled they can be modified to be meaningful
* Rails and RepresentativeStateTransfer are like [peanut butter and chinese food][1]
* Everything in routes.rb is compiled from top to bottom, meaning items at the top take priority.
* [Rails API routing][2] documentation
* Using `rake routes` in the app directory will show ALL available routes.
* Nesting is done in a block where all nested resources are placed in block. Still use `resources :models` naming method
  * This causes the parent to be the requirement (in urls/etc)
* [RoutesExamples]
* If you only need several actions use `:only => [:update, :destroy]` or `:except options`
* [CustomActions]
* [NestedRoutes]

[1]: http://youtu.be/8RUO-V9BSnc
[2]: http://api.rubyonrails.org/classes/ActionController/Routing.html
[RoutesExamples]: /RoutesExamples
[CustomActions]: /CustomActions
[NestedRoutes]: /NestedRoutes