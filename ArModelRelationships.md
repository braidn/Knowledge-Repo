* `has_one`
  * one-to-one relationship
* `has_many`
  * one-to-many relationship
* `belongs_to`
  * the model for the table that contains the foreign key always has the belongs_to declaration
  * Example being orders and invoices: an order is going to has_one invoice and the order number (foreign key) will be in the invoice model
  * these child tables belong_to a parent of some kind.
  * these can be auto added by using `table:references` with the generators
* `has_and_belongs_to_many`
  * considered a many-to-many relationship
  * used in both models (no need to use has_one or has_many)
  * active record creates a join table (named after both table names connected with a _ in alphabetical order)
