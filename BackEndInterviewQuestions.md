# Backend Interview Questions.

## Design Patterns

### Global Objects are Evil?

Most of the time these are global state wrappers more than anything. 
This leads to shared mutable state which could get changed anywhere throughout an Application. 
If shared static methods are in play, 
calling these from anywhere can be confusing due to scope or figuroing out implementation.

### Inversion of Control

Sometimes confused as _just_ dependency injection but, 
in fact encompass the observer and template design patterns. 
Another good example of this is seen in barriers between framework code and biz code. 
IoC exists where framework code calls biz code versus the other way around.

DI inverts dependencies to the injector over the class itself. 
The observer pattern (like an event bus) also inverts control to the subscribers. 
This exists in the template pattern because 
the developer implements the base/void methods in their own implementation.

### Active Record Pitfalls

AR's main problem is that the classes couple themselves highly to the underlying DB. 
Due to this, these classes often violate the Single Responsibility Principle.

### Avoiding Nils

Null object pattern (likely the most robust), 
using safe accessors, 

### Anticorruption Layer

These are basically wrapper's around a database or dependency. 
They allow a clear separation between outside code an owned code. 
Plus it leads to a less coupled design overall. 
Unlike a Facade or Adapter this layer predominantly deals with wrapping a problematic underlying API. 
This is where the name of this derives from.

### Robustnes Principle

Otherwise known as Postel's Law, 
named after Jon Postel.

> "Be conservative in what you send, be liberal in what you accept"

Otherwise be conservative in what you do but liberal in what you accept. 
This is a little tricky but if a program sends message, 
these messages should conform absolutely to the spec. 
Programs that receive messages should be able to accept non conformant messages as long as they are clear.
