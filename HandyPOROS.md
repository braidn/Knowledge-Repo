# Handy Plain ole Ruby Objects

## Query Object

* 

## Service Object

* Encapsulates a single piece of business logic.
* These objects rarely have more than one public method named `call`
* Can sometimes be found in a `/services` directory under app.
* Usually start with a verb to clue the reader into the action.
* Returns data over a simple boolean.
* 

## Value Object

* Created to encapsulate data that's easy to deduce from the object's name.
* There should be more than one piece of data encapsulated.
* This data should be immutable throughout the lifecycle of the object.
* Should return a boolean of some kind, usually in the form of equality.
  * This equality should be determined by the object's attributes.

## Form Object