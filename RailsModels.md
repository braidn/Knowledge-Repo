Explain to rails what is going on at the DB level.

* `dependent => :destroy` forces the association to rely delete it's connection if itself is deleted.
  * this is a little slow if there are a lot of items to destroy
  * another way would be to `dependent => delete_all`
  * if per chance you just wanted to zero out the related id field pass `dependent => :nullify`
* [RailsBelongsTo]
* Otherwise known as [ActiveRecord]

[RailsBelongsTo]: /RailsBelongsTo
[ActiveRecord]: /ActiveRecord