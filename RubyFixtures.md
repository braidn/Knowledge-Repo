Baseline environment for our tests to run in.

* Mostly common in [Rails][0] where you build testing fixtures (objects) for your database.
* If maintaining multiple platforms it is often best to keep a fixture per platform
* All data contained in CSV or YAML files...all comma separated.
* Base name of the file must match the name of a database table
  * In addition these files must all be plural(product == products, kiwi == kiwis, etc)
* When building them make sure to weave a succinct story instead of using arbitrary names.

[0]: /RailsTestFixtures