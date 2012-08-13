* A migration name "Order" would be considered a subclass of ActiveRecord::Base but the table name would read as: "orders"
  * Clear diff in the uppercase name vs lowercase/plural
  * if a plural needs to be correctly defined then the following code gets placed in /initilizers/inflection.rb
    * `class Sheep < ActiveRecord::Base self.table_name = "sheep" end `
* In rails console invoke `Order.column_names` to see the column names of the available model
* {{ArPrimaryKeys}}
* {{ArModelRelationships}}
* {{ArDynamicFinders}}
* {{ArCallbacks}}
* {{ArObservers}}
* {{ArTransactions}}