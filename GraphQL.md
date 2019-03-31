# GraphQL

## Notes

* Due to their being maximum control of data, versioning is basically useless.
* Nullability is a big thing and is exposed through the null type.
* Response data can be highly compressed when setting the Accept-Encoding header to `gzip`
* Authorization should be done at the business layer versus at every entry point.
* Best practices are few and far between and often times domain dependent.
  * Connections for pagination are a widely regarded one.
* Like all good API's, it should produce all businesss logic alongside data.

## Design

* Node interface:
  * very common interface that often only has an id field.
  * Handy to implement on all business objects because it hints at an item that's persistable and retrievable via an id.
* Boolean fields are almost always non null.
  * There has to be some real semantic value in null/false/true otherwise.
* There is a difference between "" and `null`.
  * an empty string can be applicable but not populated where null means not applicable.
* Attempt to focus the design around the Business Domain.
  * versus the legacy/user interfaces/implementation.
* Entity-Relationship modeling is often times a great way to design from a bird's eye view.
  * Due to the level of complexity inherent in most API's this is a good place to start.
* Enums are handy when a field can only take a specific set of values.
* Write separate mutations for separate logical actions on a resource.
  * this will almost always create more mutations but, the separation is worth saving on complexity
* When writing mutations for relationships try to think if multiple items will need changing or just one.

## Differences In Rest

* REST focuses on 'resources' where, entities are the main feature here.
