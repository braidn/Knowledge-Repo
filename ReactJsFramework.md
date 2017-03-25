# ReactJS

## Notes

* [React Patterns](ReactJsPatterns)

###Components

* `Component` is the building block behind React
* The UI layer can be though of as a tree (think BTree) of components
  * when building it is often times easier to start at the most inner and work out
  * this will almost always mean using data stubs until you get to the outer most content.
* Components have a `render()` function that creates an intermediate-DOM (HTML output)
  * this is a requirement for all components.
  * this _must_ return a single, root element. (wrap stuff in single divs)
* Calling `renderComponent()` on the root of the tree will recursively build its' entire DOM
* Components are created by creating a: `React.createClass` object
* `this.props.name` is used to read the name property passed into the creation of the class (_input_).
  * these properties are immutable and only a higher level component is allowed to make changes
* Second type of input is `state` which is mutable.
* Data flows down the Component tree while events bubble up.
* `ref` attributes are used for inputs
  * used to assign a name to a child component and referenced with `this.refs.name`
* Can use `defaultProps` to pass default props into the component.
* Can use `propTypes` as a sort of soft type definition of the props.
  * [Example](ReactJsPropTypesExample)
* Parent components can pass dom nodes to the child. These are accessible in the child with: 
  * `this.props.children`. 
  * This also means that children is a bit of a keyword and shouldn't be used to name props
* The proper way of retrieving information from the children is by using props (passing callbacks)

####Container Components

* Only deal with logic required to generate presentation components.
  * 'logic' mentioned here is the data (state) and functionality/behavior (events).
* These are often time's classes that are extended from the component class.
* Bind presentation components with a store of some type.
  * this could be redux/relay/flux/etc
* Container components themselves should subscribe to these store objects.
  * due to this, one might have to manually call the subscribe/unsubscribe during the component lifecycle functions.

###DOM Sync

* Whenever a call to `setState()` is made React triggers the `render()` method to keep in sync
  * this is just another way from `React.renderComponent()` to force a visual refresh
* The DOM diff is done through a virtualDOM which is not a shadowDOM
  * shadowDOM's are browser specific, this is not.
* Use `getDOMNode()` on a component to grab it's native DOM element. (handy in getting input data)

###Synthetic Events

* Events that are exposed at the intermediate DOM level.
* React uses [event-delegation][1] therefore only attaching events to the root-level.
* Used to standardise UIs across browsers/devices.
* All event handlers are written with a camelCase convention: `onSubmit`.
* Always return `false` from an event handler to prevent browser's default actions.

###State Machine

* Component lifestyle has three distinct states:
  * Components are breathed into life by being _mounted_
  * Components are placed in an _update_ state when `setState` or `setProps` is called
  * Components are _unmounted_ when they no longer are generated from `render`
* Between updates, React diffs the deltas and updates only the required elements
  * pretty much sums up why it is so awesome.

###Fetching Data

* Most of the time fetching will be done with third party XHR libs (Fetch/Axios/Superagent)
* Most common place to write this code is in the `componentDidMount` function.

###With Rails

* So far it seems like everyone is using the react rails gem
* Make sure to add declaration below turbolinks in `application.js`
* Use `config.react.variant = :development` in development for unmagnified assets
  * the alternative of this is :production which removes all the helpful warnings.
* In .jsx files this is required at the beginning for compilation: `/** @jsx React.DOM */`

###Testing

* When testing composed components, make sure to shallow render. This will render the component but not it's children. Otherwise tests can and will get pretty heavy.

###External links

1. [Docs][2]

[1]: http://davidwalsh.name/event-delegate
[2]: http://facebook.github.io/react/docs/getting-started.html
