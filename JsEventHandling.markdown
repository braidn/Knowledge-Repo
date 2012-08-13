* Event Handling: associating and event and an object with a specific function
* 4 different ways to create an event listener
* It is possible to remove event handlers by assigning null to the event

### Traditional Event Listener

* `window.onload = init;`
  * The problem here is that one function can be called on one event
  * If you wrap multiple events in a function of it's own, you can mitigate this issue

### W3C Event Handling

* A terse, yet reliable and well developed cross browser spec (IE>9)
* Method based that uses `.addEventListener('1',2,3);` or `.removeEventListener('1',2,3);`
* The three arguments are
  1. event type
  1. function to be used
  1. boolean for the specific event phase (false is also OK)
* Watch the quotes around the actual name of the event
* Older versions of [IE][1] use `.attachEvent();` and `.detachEvent();`
  * and instead of taking 3 take 2 arguments (same order as above)
  * also it uses the onload syntax in the event instead of just load (like the W3C version)

###Notes

* Functions for forms will often times return false but not true with keypress and click events.

[1]: http://iehatersclub.com/