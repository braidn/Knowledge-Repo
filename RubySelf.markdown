Otherwise known as the current or default object

* Best way to track self is which object was last method receiver.
* Self is automatically set to object main.
  * This is often times called the top level context or top level of the call stack
* Self in a module or class automatically is set to the name of the class or module
* If an internal method within a method is fired it re-looks up the object ancestor chain.
* IF redefining self method, it is often times best to do it before defining the initialize method