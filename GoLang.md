# Go Lang

### General Notes

* Go is an OO style language with no classes.
* Printing can be done with `println` and `print` functions.
  * However importing the fmt package and calling `fmt.Println` and `fmt.Printf` is more favorable.
* Programs begin their execution in the main function.
  * This can be thought of as the entry point of the software.
* _Only_ constants are immutable.
  * However since arguments are passed by value, these original values won't be mutated.
* Code organization (just a general idea and gofmt might not do this):
  * List of Packages for import
  * Constants
  * Variables
  * Main Types (Structs). Try to keep this as small as possible per file.
  * Functions
  * Methods

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

### Collections

* Arrays uses bracket style notation and can be created with a set length: `var a [23]int`
  * Access to the items in the above array: `a[1]`
  * Values can be passed on initiation: `a := [2]int{1,2}`
  * The splat operator can be used to lazily assign a length: `a := [...]int{1,2}
* Multi dimensional arrays are completely ok: `a := [2l][1]int`
* _Slices_ are a bit more common, they are basically an interface wrapper for the array.
* Slice example: `p := []int{1,2}`
* Slices simply hold reference to an underlining array.
* Slices can be sliced where the new array will refer to a subsection of the original.
  * ex: `someSlice[1:22]`
* Slices can be created with the `make` keyword instead of using the slice literal context.
  * ex: `make([]string, 3)`
* The append function can be used to add values to a slice.
  * ex: `append(slice, ("some", "values")`
* _Range_ function is used to iterate over a slice.
  * ex: `range slice { do something fun }`
* When iterating like this using a for loop, the location and value of the slice are passed in.
  * the programmer needs to use an underscore if they don't want use one or the other in the function block.
* `break` and `continue` are key words used to skip or stop iteration of a slice.
* _Maps_ are hashes or structures where there are keys and their respected values.
* When maps are not created from the literal syntax they can be created using `make` as well.
* To delete a key from a map, the `delete(map, key)` ifdks used
* To test that a key is in a map: `val, ok = map[key]`

### Control

* `if`s can begin assign scoped variables which are only in scope of the `if`
* The only looping structure that Go has is the `for` loop.
* `For` loops are very remensicent of JS but without the need of `()`
  * however they can be written like a while loop: `for sum < 100 { do something }`
  * and infinite loops are completely ok to the compiler: `for { do something }`
* `Switch` statements exist in Go allowing the avoidance of nasty if/else statements
  * only values of the same type can be compared using the `switch` statement
  * like Ruby, a default value can be set if all conditionals fail
  * conditionals can be expressions that get assesed prior to comparing: `case 1 - ten:`
  * Due to conditionals, you can have multiple values as well: `case 1, 2, 3:`
  * The `fallthrough` keyword will evaluate the switch block and continue to evaluate the rest.
  * And of course the `break` statement will stop execution completely. 

### Methods

* There is the concept of a function and a method in Go
  * method's have defined receivers much like classes and methods in Ruby
* Methods can be defined on any type defined in the package
  * However, methods can not be defined from another package or basic types
* Pointer receivers are favorable for methods due to not copying values on each call.
* Pointer receivers are also favorable because they allow the programmer to modify the pointer value.

### Interface 

* A kind of type that is defined by a set or collection of methods.
* These can be glue between structs and more simple/generic functions.
* New types can quickly implement these interfaces and get access to these functions.

#### Errors

* Errors are an interface that with a single `Error` method that returns a string.

### Concurrency

* Variables are not shared across goroutines and therefore prevent race conditions
* A goroutine is a lightweight thread managed by the Go runtime.
* These are created by using the simple `go` keyword
* Goroutines are also used to push items into channels without causing deadlock
  * This occurs due to the main thread working on the channel and the groutine waiting

#### Channels

* Channels allow the sending receiving of values through the `->` operator.
* Data always flows in the direction of the arrow.
* Channels can be created using make: `ch := make(chan int)`
* These can be buffered, to do so add the length as a second argument.
  * ex: `ch := make(chan int, 100)`
* Channels are unlike files, where they don't need to be explicitly closed

#### Sender and Receiver

* Senders are used to close a channel to indicate no more values are available/allowed.
* Receivers can test if a channel has been closed

  * Buffered channels will only send to the block when the buffer is full.