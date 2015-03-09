## General

* Relies heavily on keys of which can't have whitespace

### Helpful Commands

* `redis-cli` to actually connect to the cache
* `flushdb`: flushes entire key store of the current db
* `flushall`: works a little better

### Hashes

* Key and sub-key values define a object
* Think of a big tree. One beginning and branching outward

### Rails

* Use `flushall` above when `Rails.cache.clear` is failing