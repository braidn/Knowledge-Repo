#State Design Pattern

## Notes

* Often times though of as smaller, stand alone state objects over monolithic state machines.
* State's changed by changing the pointer from context to the correct state.
  * in many cases the context object is the actual object in the system. This isn't a requirement though.

## Objects in an OO State.

1. Context: Interface for states/object in state to the outside world. Holds a pointer to state.
1. State Base: Base, inheritable layer for all other states to inherent from.
1. States: List of states that define certain bits of business logic for the specific state.

### Context

* Unable to directly change the state from one state to another.
  * however, this will need to know how to set the initial state of an object.
* Does not know what exact state its at without interrogating the underlying state object.

### State Base

* Abstract base class that implements methods for all the concrete state classes.
* Super high level class that, in Ruby would create a few base methods.

### States

* Contains all business logic to implement decisions based on the state. 
* All before and after transition logic should encapsulated in theses state objects.
* These objects become the goto place in a system to implement methods that deal with state or transitions.