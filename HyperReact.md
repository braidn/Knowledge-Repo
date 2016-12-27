#Hyper React

##Notes

* Opal based gem that wraps ReactJS.
* Allows a developer to think in a single language for both back-end and front-end
* Unfortunately not able to use vanilla-ujs since Opal jQuery is a requirement.
* There seems to be a requirement for therubyracer here as well. 
  * this is actually super bizarre and a little disturbing.
* When passing keys to child elements, make sure to pass them as their own param.
  * instead of passing them in a data param.
* Params can take proc's as values and will be assigned `.call` when the param is accessed.
* `State` can be updated and re-rendered if a ! is used on the variable writer.
* Children can be passed to the creation of a component.
  * A special keyword `children` is available to iterate over each one and `render` can be used to render them individually or as a collection.
* There is a [litany of events that can be listened for][1]
* Almost always we will use: `react_component('NameSpace::Name', params)` to render a component.

##Params

* Much like in React, these props need to be defined using the `param` keyword
  * This keyword which is so close to `params` which is used to get params passed to a component, can be confusing.
* These can have defaults, they can allow nil, and they can have strict type definitions.
* `State` is accessed just like params using the `state` variable in the component.


##Lifecycle Hooks

* Can be written as a block or take the name of an instance method as a param.

[1]: http://ruby-hyperloop.io/docs/event_handelers/