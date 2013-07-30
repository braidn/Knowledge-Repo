##Notes

Classes are objects as well and due to that, they have instance methods...of sorts. Most of use the `.new` instance method a whole lot when creating new objects.

* Worth remembering: Class is a subclass of Module
* All class definitions are executable
* Defined one method at a time
  * This would mean that if a method is defined twice in a class, the last instance would be the one that fires

###Overiding

* a call to super will look into the class where inheritance took place and call the method
* we can use `:alias_method :desired_name, :parent_name` to specifically call the child method
