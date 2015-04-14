# Postgres Hstore Extension

## Notes

* All values stored a strings
* Access is done like hashes `something[:fun]`

### Requirements

* These columns need to be indexed and can be done so in two ways:
 * GIN: indexes are three types faster to search, but they take more time to index. They also take more disk space. Use it when you have more than 100K unique terms.
 * GiST: indexes are slower than GIN indexes, but they’re faster to update. Use it when you have up to 100K unique terms
* When using Rails you can just use the `add_index` syntax
 * ex: `add_index :users, :preferences, using: :gin`