# Rails Upgrades

## 4.2 -> 5

* Use the handy `rake rails:update` task to weed through configuration changes.
* `cors.rb` introduced to finally be able to control CORS in one central place.
* Models that are AR backed inherit from `ApplicationRecord` not `ActiveRecord::Base`
  * Not a requirement, the app should boot just fine without changing these.
* Params internally are no longer a hash but a `ActionController::Parameters`
