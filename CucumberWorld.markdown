* Special keyword for mixing in certain helper functions to dry up code
* Especially helpful when dealing with the need of instance variables
* The main way you’ll use the World is by extending it with modules of code that support your step definitions by performing common actions against your system
* If you wanted to see everything that gets mixed into World you could add `puts self` into any step definition