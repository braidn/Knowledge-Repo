# Go Lang

### General Notes

* Printing can be done with `println` and `print` functions.
  * However importing the fmt package and calling `fmt.Println` and `fmt.Printf` is more favorable.
* Programs begin their execution in the main function.
  * This can be thought of as the entry point of the software.
* _Only_ constants are immutable.
  * However since arguments are passed by value, these original values won't be mutated.

### Imports

* Generally found at the beginning of the code, especially if using gofmt.
* Can be a single string or a web url.
* `go get` is the command to pull down these packages.

### Exports

* Variables and functions are exported from their imports
* These names are always titlecased.

### Functions

* Types are defined after the argument names.
* A single type is declared before the opening parens denoting the return type.
* There can be any number of return values for a function.
  * These return values, when more than one are called 'result parameters'

### Pointers

* Go passes arguments by value, which means copies of the arguments are created.
* This can be mitigated by passing a pointer to a value.
* To access a pointer to a value use the `&` in front of the value.
* To dereference a pointer simply add a `*` in front of the value.

### Structs (a kind of type)

* Collections of fields and their properties.
* Lightweight classes that support composition but, not inheritance.
* No need to set up getter or setter functions, this is done for you.
* Structs can be created, assigned to a var and updated with by using: `var.field = val`
* The keyword `new` can be used to initialize a zeroed value of the type and return a pointer to it.

### Composition and Interfaces

* Since GO has no inheritance it relies on these two terms.
* Different types can be embedded in other types to achieve composition.
* Dot notation or combining struct literals can be used to assign values to these fields.
  * Maybe hard to imagine but looks just like JSON.
  * Also any methods defined on one type are accessible by other composed types.
* If a struct has an interface and it composes itself to another struct, the interface is shared.
* When structs get big and crazy look to use pointers to save on memory allocation.