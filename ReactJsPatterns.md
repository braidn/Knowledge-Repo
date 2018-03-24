# React Patterns

## Notes

* Components can be thought of as their own little isolated systems.
  * They have their own state, input and output.
* Using `props.children` we can keep our composed functions agnostic and dependency free.
  * this is due to pretty much anything be able to be passed down through props.
* If we need to get reference to a DOM element there is the [`ref` keyword][2]
* Extracting components into their smallest possible state will lead to more and more testability.

###Component Hierarchy

* This is best thought of as an outline of the application.
  * Which components will live in others, etc.
* A sensible way to construct this would be to take your component hierarchy and build it with mock data.
  * building this static version takes a lot of typing but little thinking.
  * Once finished, the interactivity part can occur which takes little typing and lots of thinking.

#### State

* Passing of data from parent to child in this model should only rely on props (not state).
  * state is reserved 99% of the time for interactivity.
* When building this static version, on can go bottom up or top down. 
  * In larger, more complex apps, it's more advantageous to start bottom up and test.
* When starting, a team should come up with the most minimal amount of mutable state.
* Three good questions to ask when figuring out state:
  1. Is it passed in from a parent via props? If so, it probably isn’t state.
  1. Does it remain unchanged over time? If so, it probably isn’t state.
  1. Can you compute it based on any other state or props in your component? If so, it isn’t state.
* It's also best practice to figure out what component should own the state.

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
  * to get around the unwieldiness, use a POJO that has a get and register function to add items to a JS object. 
  Then pass this interface into the contextTypes and it should make dealing with them much easier.

###One-way Data Flow

* Core tenant of React. Data flows from the top most component down through children and never up.
* Relies heavily on ripping all data management out of components.
  * This usually introduces the concept of a store (Redux/Mobx/Flux).
* Components become 'dummy' representations of their data stores.
  * this makes them extremely easy to reason about/test/etc.


[1]: https://facebook.github.io/react/docs/context.html
[2]: https://facebook.github.io/react/docs/refs-and-the-dom.html
