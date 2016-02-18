# Active Record Querying

* When searching for columns without nil/nulls: `.where('something is not null')`.
* the `OR` for `where` clause can be an array:
  * `Product.where(channel: ['mobile', 'ios', 'android']).
  * Will return all products that have a channel of 'mobile' or 'ios' or 'android'.