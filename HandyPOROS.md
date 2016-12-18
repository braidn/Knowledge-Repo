# Handy Plain ole Ruby Objects

## Query Object

* [Wraps and obfuscates ORM specific code][1]
* Often times only has one of two public methods: `data` or `query`
  * This clues the reader into the what type of data the object returns

## Service Object

* Encapsulates a single piece of business logic.
* These objects rarely have more than one public method named `call`
* Can sometimes be found in a `/services` directory under app.
* Usually start with a verb to clue the reader into the action.
* Returns data over a simple boolean.

## Value Object

* Created to encapsulate data that's easy to deduce from the object's name.
* There should be more than one piece of data encapsulated.
* This data should be immutable throughout the lifecycle of the object.
* Should return a boolean of some kind, usually in the form of equality.
  * This equality should be determined by the object's attributes.

## Form Object

* Least favorite of all these abstractions.
* Usually used when the controller or service needs to talk to the DB.
* VERY popular when wanting to remove validations from Rails models.
* Seemingly much more useful when a form updates multiple or many models.
* Again if using rails, these usually mixin `ActiveModel::Model`.

[1]: /ActiveRecordQuery#best-practices