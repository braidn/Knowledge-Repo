##Notes

###Methods

* `to_json` should be used to consume json objects/representations
* `as_json` is used to create said representation
* `to_json` wraps the item in extra quotes, where `as_json` doesn't
  * this is likely do to the fact that if `to_json` is called, Rails creates the 
  object using `as_json` then the hash is encoded as a json string (extra quotes)
