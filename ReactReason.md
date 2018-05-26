# React Reason

## Notes

* All of your HTLML is type safe/type checked in ReasonReact.
  * This means if you misspell an attribute, the compiler will warn you.

## Components

* There are two types of components available:
  * Stateless (similar to functional components in React)
  * Statefull items that contain state and reducers (React.CreateClass)
* These are not classes or functions, they are Reason records.
* Each record have many of the React lifecycle/render/state avaiable.
  * Almost all of them are overridable in the make function that returns the componet
    from the module.
* Because it's immutable the object is spread out (spread operator), altered and a
  new component returned

## Rendering

* Many times you will use a Reason List to build a list of items.
  * then it's quite common to turn this into an Array that React can render using `Array.of_list`

## Methods

* `render(self)`: Most commonly overriden method.
  * the argument gives us access to state/reducers.

## JSON

* Think of loading the JSON in the term of states.
  * Has it loaded, did it fail, what does the success return?
  * Many times this state can be represented back to the UI layer.
* Wrap whatever library you are using in the Js.Promise function provided by bucklescript.
* Most of the time, return an option and pass the result of the fetch to `Some(jsonResult)`
  * Any errors can be passed to the `None` part of the option type (Reason Option Type).
