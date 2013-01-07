##notes

* Created by: `class ClassName`
* Come with some magic methods that are prepended with double underscores("\_\_")
* Like in most languages, to instantiate a new object call `new Class` and assign it to a variable
* Methods or properties of the Class are reached using `->`
	* Otherwise known as the object operator
* Static properties are accessed using the `::` operator
	* These are class level properties and never descend into instantiated objects

###NameSpacing

* This is done by calling `namespacing name` at the top of the file.
* Then all classes defined in that file can be called by `NameSpace\ClassName`
	* Odd implementation, but PHP needs it like no tomorrow.
