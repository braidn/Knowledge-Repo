# Active Record Querying

# Notes

* When searching for columns without nil/nulls: `.where('something is not null')`.
* the `OR` for `where` clause can be an array:
  * `Product.where(channel: ['mobile', 'ios', 'android']).
  * Will return all products that have a channel of 'mobile' or 'ios' or 'android'.
* There are two different ways to load associations into finders:
  * `.joins` will lazy load the associations passed in.
  * `.includes` will eager load the associations when passed in.

# Best Practices

* Return a relation versus executing the query.
  * chain able scopes are easier to use.
  * these relations can be used with `merge` which is super handy.
* Filtering and Sorting in Ruby will be 100x slower than in the database.
* Indexes kick total ass when upping the performance rating.
  * good practice: index on all id columns and anything used in a where clause.
* Complex queries can easily be pulled into query objects.
  * returns a blob of data (`.data` method) or a relation (`.relation` method).
  * SRP class that's great for code organization.
  * Easily testable.
* Avoid ad-hoc generic query methods outside of scopes and query objects.
  * These are notoriously harder to test.
  * Completely unusable from a reusable standpoint.