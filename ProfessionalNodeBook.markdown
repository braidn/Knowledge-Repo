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
