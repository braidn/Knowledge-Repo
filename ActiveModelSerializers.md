* Gem to easily control the serialized json out put in rails.
* Can be tweaked via an initializer file
  * say we wanted to rid ourselves of the root node: `ActiveModel::Serializer.root = false`
  * this also can be done with `ActiveModel::ArraySerializer` as well.