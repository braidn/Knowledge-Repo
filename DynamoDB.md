# DynamoDB

## Notes

* Supports both key value and document store style of NoSql
* Guarantees consistent latency no matter the size. 
* Aggregating items that belong together (versus splitting them into different tables) is the power
* No limit on the amount of data stored but each item can not exceed 400KB
  * Nesting constrained to 32 levels.
* Read and write through out can be changed without the consequence of downtime.
* Constructed of items and attributes
  * Items are a bit like rows in a conventional dB 
  * Attributes are more like columns 
  * Has a nearly real time write ahead log called streams. 
  * Global secondary indexes really are mirrors of the first table but with new primary keys.
* There is a very _real_ iterative process to building a schema.
  * it involves review => review => review to get it somewhat correct.
  * Something like JSON Schema can be used to document each item type in a table.
* It's somewhat common that joins are not possible or should be avoided.
  * This is more true at the server level, joins (especially using [GraphQL][gql]) can be done at the App level.
* Naming of items (ie collections) differ between each NoSQL implementation.
* It's easiest to think of a DynamoDB as one big hash/map

## Keys

* Primary keys have a myriad of names:
  * PK, Partition Key, Hash Attribute
* Primary keys can also be comprised of two attributes (composite)
* The second key that is required is the sort key
* Items can have the same primary key value as long as their sort keys differ 

## Write

* All write ops will overwrite an existing item with the primary key.
* Atomic counters exist. Meaning incrementing/decrementing uncoditionally and without blocking.

## Query

* Searched by primary key and or sort key.
* Able to use filter attributes and filter expresiions.
* Maximum return is 1MB.
* Look to build querys or results that minimize round trips to hydrate data

## Data Modeling

* Traditional modeling replaced by Domain Driven Design and Physical Schema Design
  * Again, with [GraphQL][gql] we could build the schema, commit it with mocks, and see how it 'works'...
  * from there, the modeling of the Items could be hardened and implemented into a data API.
* These process should/could be hand and hand with agile style processes.
* Lot's of people feel the model here should be 'query driven'.
  * Again, this works nicely with the [GraphQL][gql] concept
* Perhaps it's good to think at the level of: 1 click per document.
  * This is of course very 'web like'. How would 1 click per document work for a mobile app?
  * The idea being, what's the smallest shippable payload for the current screen?
* When in absolute doubt, reach for embeding documents/data versus referencing (joins).

## Relationship Patterns

* One => One: embed
* One => Many: embed vs referencing
  * One => Few: embed
  * One => Many: ref
  * One => Zillions: ref (sub table with DynamoDB)

## Data Modeling Steps

1. Always start with something high level, using a google sheet while boring can help think out top level schema.
2. Bring these ideas into the DynamoDB interface or a GUI locally.
3. Check the design to see if it satisfies the current queries
4. If yes, go to code, if no, go back to the beginning.

[gql]: /GraphQL
