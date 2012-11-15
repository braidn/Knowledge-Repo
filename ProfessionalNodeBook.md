##Notes

* __Event Callbacks:__ functions that are fired off when some event
finishes
* Event driven and asynchronous programming are pretty much the same
thing.
  * You are looking for results to be passed into events instead of
  simply looking for the result
* The way it gets around I/O lock is through an _event loop_
  * event loops are basically a do while that never ends and only does
  two specific things
    1. Event Detection
    1. Event Handler Firing
* JS has no I/O lib

###Node Modules

* Uses CommonJS modules instead of JS' global namespacing
* `var module = require('module name');`
* Three overall different kinds of modules
* Core Modules: modules that are bundled with node. Require just the
name.
* File Modules: Loaded by calling an absolute path from the file system
* Folder Modules: Loaded from looking into a specific directory. Usually
searches for a `packages.json` file.

###Buffers

* How node handles non text objects (aka binary data)
* easiest way to create a buffer = `var buffer = new Buffer('somestring','encoding');`
* if you create a buffer by calling `var buf = new Buffer(1024)` the
resulting buffer is not filled with 0s but rather random bytes
* the `.length` method is used to get the length of a buffer. Ala, you
can use this in a for loop to iterate over each byte.
* buffers can be decoded by calling `.toString();` method on them

###Event Emitter Pattern

* The pub/sub pattern of callback listening on event firing
* Node supplies an `EventEmitter` class as a base to create user defined
event emitters
* event types are typically lowercase and devoid of spaces
* the `.addListener();` and `.on();` methods are used to bind event
listeners to objects
  * multiple event listeners can be bound to the same object. Both will
  fire in the order they were registered
* `removeListener();` is used to remove an event listener
* `.once();` is used to invoke the event listener only once.

###Scheduling Events

* Great for delayed interactions
* `setTimeout();` is used to set a function to fire in the future
  * `clearTimeou();` used to remove the setTimeout before fired (last
  chance)
* `setInterval();` is like setTimeout however it runs on a given
interval, not just once.
* `nextTick();` will defer something until the next event loop
* Node and Javascript are generally single-threaded event loops
