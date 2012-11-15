Ruby modules act super cool. They wrap themselves as an anonymous class and injects themselves into the Ancestor chain.

* Also known as include classes and even sometimes proxy classes.
* When a module is included it bumps to right above the object chain right after the method.
  * If another module is included directly afterward it bumps the first module up the chain and the second is right behind the current method. Lookup [RubySelf][1]
* Most often USED to create a sort of namespace for methods so not to stomp on existing methods along the call stack.
* May contain methods, classes, constants and even other modules
* The namespace to get at classes in a module is: `ModuleName::ClassName`
  * constants can also be accessed this very same way
  * you can also just include one big `include ModuleName` at the beginning of the file (or where ever) to not have to use the double colon method.
  * nesting can occur so you could type `Module1::Module2::ClassName`
* Name spacing can come from a myriad of files through require statements that in reality "stitch" all the files together.
  * This concept is hard to really put down on paper.

###As Mixins

* Solves the problem of sharing code between otherwise unrelated classes
* To include in a class simply call: `include ModuleName` at the beginning of the class definition and BOOM, success
  * all of the module's methods automagically become available to the class that the module was included in
* To include modules as singletons, or class level methods, instead of calling `include`, call `extend ModuleName`
* Mixin modules are clever namespaces to include constants

[1]: /RubySelf