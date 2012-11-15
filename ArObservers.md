create: `rails g observer modelName`  
mod: So they don't work out of the box, config/application under module ProjectName should read = `config.active_record.observers = :list_of_observers.` Within the list use the name of the model first, then underscore, then the word "observer"

* use: Allows abstraction in the models. Stops the fat model business, worth looking into more.
  * An object that transparently links itself into the model class