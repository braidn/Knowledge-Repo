* Ruby keeps three different time based systems.
  1. A programming standard Unix C lib
  1. Ruby Specific Date
  1. Ruby Specific DateTime
* The latter two are much slower than the UNix version...duh!
* ActiveRecord uses the Date/DateTime stuff