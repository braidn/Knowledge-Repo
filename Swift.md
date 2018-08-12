# Swift Language

## Notes

* Variables are constructed using Hungarian notation, much like JavaScript

## Primitives

* `var` is used to instantiate variables
* `let` is used to build constants
* The `+=` and `-=` can be used shorthand for incrementing variables

### Optionals

* The idea of earmarking a variable for future use.
* A type signature must be passed during the instantiation process:
* ex: `var someFutureString:String?`
* When optionals are assigned they need to be 'unwrapped' they can be done so forcefully:
  * ex: `someOptional!`
* Or they can be optional assigned using an `if...let`:
  * ex: `if let value = optional { print(value) }`

### Strings

* Interpolation is done using the following syntax: `\(variable)`

### Ranges

* Much like Ruby Ranges, they have a closed and open variant:
  * ex: `let range = 1...10` (1 through 10 'included')
* Half closed ranges exist!
  * ex: `let range = 1..<10` (1 through 9 'included')
* One sided ranges also are available, for iterating indefinitely in a single direction:
  * ex: `for name in names[2...] { print(name) }`
  * this is also how we access items in an array.

### Functions

* Fairly similar to the older JS syntax:
  * ex: `func greet() { print("Hello") }`
* executing the code is as easy as calling the function:
  * ex: `func()`
* When passing arguments to functions, these need to be typed:
  * ex: `func(name: String) {}`
  * arguments are much like keyword arguments from ruby, the `name` var is available in the function scope.
* Functions also need return signatures:
  * ex: `func(name: String) -> String {}`

## Collections

### Arrays

* Types matter in Swift and therefore we need to construct arrays that have knowledge of their underlying types:
  * ex1: `let integers: [Int] = []`
  * ex2: `let integers = [Int]()`
  * 2 ways of creating the same array.
* Array construction can skip the type signature if initial values are included (type inference)
* Arrays can be concatenated into other arrays using some helper methods on an Array instance:
  * ex: `states.append(contentsOf: ['Dominican Republic', 'Bollova'])`
  * This also has a shorthand: `array += array` when saving on characters.
* Items can even be inserted at specific locations in an array:
  * ex: `states.insert("Ohio", at: 4)`
* Getting a value at a specific index is as easy as: `arrayName[4]`
* Since programmer's can not be sure that a value exists at index 4, use `if...let` for safety.
  * ex: `if let value = states.index(of: "Florida") { print(value) }`

### Dictionaries

* Just like in Ruby, these are unordered lists of key value pairs.
* To create a dictionary, we have two ways (like Arrays):
  * ex1: `let dict = Dictionary<String, String>()` (this is the longhand way and should be avoided)
  * ex2: `let dict = [String: Int]()`
* Of course, we can create a dictionary with example values to take advantage of type inference
  * ex: `let pizzaDict = ["veggie": 14.99]`
* Keys are accessed just like indexes in arrays:
  * ex: `let veggie = pizzaDict["veggie"]`
* Updating keys is the same as accessing except there is an `= someValue` to overwrite the existing value.
  * this is somewhat unsafe though. What if the value accessed didn't exist? A fix for this:
    * ex: `dictPizza.updateValue(13.99, forKey: "veggie")`
  * this will also add the key if it isn't available in the dictionary.
* Iterating over values in a dictionary is easy using the `for...in` loop:
  * ex: `for values in dictPizza.values { print(values) }`
* This iteration can be done for keys as well:
  * ex: `for key in dictPizza.keys { print(key) }`
* To iterate over each key/value pair:
  * ex: `for (key, value) in dictPizza {pring("\(key) \(value)")}`
* Just like there is an `updateValue`, there is a `removeValue(forKey)` to remove key value pairs.

### Sets

* Sets are basically identical to Ruby: storing unique values in any order.
* Creating sets: `Set<String>([])`
  * this empty array is called an 'array literal'.
  * an empty array, or a list of values can be passed as the array literal.
* Items can be added to a set using the `set.insert(item)` method.
* Set's can be interogated using the `contains` method:
  * ex: `if set.contains('Big Fish') { print("Found IT!") }`
* Iteration can occur using the `for...in` loop:
  * ex: `for movie in favMovies.sorted() { print(movie) }`
* Because Set's are unique, the intersection between two sets is quite easy to find:
  * ex: `set1.intersection(set2)`
* This uniqueness, also makes joining two sets easy as well:
  * ex: `set1.union(set2)`
* Because a Set is an array, methods like `remove()` and `removeAll()` also work on them.

# Logic/Control

* `if/else/else if` statements are written like JS but without the surrounding `()` items.

## Looping

* `for...in` loops iterate over values found in ranges/enumerables.
* `while` loops just like every while loop in any language.
* `repeat...while` loops are similar to `while` but evaluate conditions for the next iteration at the end of the loop.
  * ex: `repeat { doSomeWork(work) } while work <= done`
