These are kinda tricky. Any time you see a `def` this is considered an instance method (instead of just a "method). This is true because you require an instance of the class to call the method. Kinda confusing? Yeah definitely but just remember if there is a need to call `Myclass.new` and create an object to get at the methods they __ARE__ instance methods.

* when calling a method you usually call it with `obj.method`
  * you can also call `obj.send(:method, args)`
  * `obj.public_send()` respects privacy within the application
    * Otherwise known as {{DynamicDispatch}}
    * Pattern Dispatch is identical except with {{RubyRegexp}} patterns instead of {{RubySymbols}}
* 3 forms of visibility: {{RubyPrivateProtectedPublicMethods}}