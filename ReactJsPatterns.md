# React Patterns

## Notes

* Components can be thought of as their own little isolated systems.
  * They have their own state, input and output.
* Using `props.children` we can keep our composed functions agnostic and dependency free.
 * this is due to pretty much anything be able to be passed down through props.

###Higher-order Components

* Look very similar to [the decorator design pattern](JsDesignPatterns#pattern-list_decorator).
* They wrap a component in order to add new functionality to the underlying component.
* All config info is hidden in the higher order function.
  * this provides a component that is easily testable and compostable.

###Dependency Injection

* Not technically a pattern but used so much that it can be though of as one.
* Most solutions for DI in React are based on context/s.
  * Redux uses `connect` and `Provider` to interact with context.
* [Context][1] or contexts act like event bus for data throughout different components.
  * these need to be specified exactly using `childContextTypes` and `contextTypes`.
  * due to that, using contexts can be somewhat unwieldy.
  * to get around the unwieldiness, use a POJO that has a get and register function to add items to a JS object. Then pass this interface into the contextTypes and it should make dealing with them much easier.

###One-way Data Flow

* Core tenant of React. Data flows from the top most component down through children and never up.
* Relies heavily on ripping all data management out of components.
  * This usually introduces the concept of a store (Redux/Mobx/Flux).
* Components become 'dummy' representations of their data stores.
  * this makes them extremely easy to reason about/test/etc.


[1]: https://facebook.github.io/react/docs/context.html