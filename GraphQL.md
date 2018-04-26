# GraphQL

## Notes

* Due to their being maximum control of data, versioning is basically useless.
* Nullability is a big thing and is exposed through the null type.
* Response data can be highly compressed when setting the Accept-Encoding header to `gzip`
* Authorization should be done at the business layer versus at every entry point.
* Best practices are few and far between and often times domain dependent.
  * Connections for pagination are a widely regarded one.

## Differences In Rest

* REST focuses on 'resources' where, entities are the main feature here.
