###Components

* `Component` is the building block behind React
* The UI layer can be though of as a tree (think BTree) of components
* Components have a `render()` function that creates an intermediate-DOM (HTML output)
  * this is a requirement for all components.
* Calling `renderComponent()` on the root of the tree will recursively build its' entire DOM
* Components are created by creating a: `React.createClass` object
* `this.props.name` is used to read the name property passed into the creation of the class (_input_).
  * these properties are immutable and only a higher level component is allowed to make changes
* Second type of input is `state` which is mutable.
* Data flows down the Component tree while events bubble up.

###DOM Sync

* Whenever a call to `setState()` is made React triggers the `render()` method to keep in sync
  * this is just another way from `React.renderComponent()` to force a visual refresh
* The DOM diff is done through a virtualDOM which is not a shadowDOM
  * shadowDOM's are browser specific, this is not.

###Synthetic Events

* Events that are exposed at the intermediate DOM level.
* React uses [event-delegation][1] therefore only attaching events to the root-level.
* Used to standardise UIs across browsers/devices

###State Machine

* Component lifestyle has three distinct states:
  * Components are breathed into life by being _mounted_
  * Components are placed in an _update_ state when `setState` or `setProps` is called
  * Components are _unmounted_ when they no longer are generated from `render`
* Between updates, React diffs the deltas and updates only the required elements
  * pretty much sums up why it is so awesome.

###With Rails

* So far it seems like everyone is using the react rails gem
* Make sure to add declaration below turbolinks in `application.js`
* Use `config.react.variant = :development` in development for unmagnified assets
  * the alternative of this is :production which removes all the helpful warnings.
* In .jsx files this is required at the beginning for compilation: `/** @jsx React.DOM */`

###External links

1. [Docs][2]

[1]: http://davidwalsh.name/event-delegate
[2]: http://facebook.github.io/react/docs/getting-started.html