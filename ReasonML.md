# ReasonML

A Javascript/OCaml ecosystem.

## Notes

* Syntax wise, very similiar to Javascript.
  * [This Cheatsheet describes the differences][cht]
* Like Typescript and Elm, types are used heavily when defining objects:
  * ex: `type point = { x: int, mutable y: int }`
* Reason has no concept of null/nil, much like Elm.
* Iterators are somewhat like Ruby/Coffeescript:
  * `1 upto 10` or `10 downto 1`
* There is the concept of blocks in the language:
  * `let x = { some expression }`
* For and While loops are supported where needed.
  * This is likely in a few places due to the pattern matching power.
* The language itself supports a form of JSX that's quite terse.
  * This though can be easily levergaged by Reason-React

## Functions

* Functions are defined like es6 fat arrow functions.
* They can be either single line:
  * `let someFunc = (name) => "Hellow" ++ name `
  * or multiple lined using the block syntax

### Arguments

* Reason *enforces* arguments to every function.
* If a function doesn't require a argument, a unit: `()` is passed instead.
* Arguments can be labeled if needed.
  * ex (called 'punning sugar'): `let mapCoordinates = (~y, ~x) => ...`
  * when calling: `mapCoordinates(~x=44, ~y=34)`
  * with named arguments we can reorder them as needed or whichever makes sense.
  * this can be made further explicit: `let mapCoordinates = (~lat as x: int, ...) => ...`
  * The function will be called with the lat name and the block will utilize the x name
* Currying is completely built in.
  * Any function can be curried and this currying is optimized by the language.
* Optional arguments are defined as: `let mapCoordinates = (~color=?...) => ...`
  * The standard lib has an option type and that's what color would be.
  * These can be passed a 'default argument' which set's their type as the value passed.

## Control Flow

* If-else exists but it's not super used due to pattern matching (large part of language).
  * a ternary exists but again, is not used a whole lot.

## Types

* Types can accept arguments (generics) which lead to composability and easy reuse.
 * ex: `type intCoords = (int, int, int)`
 * use: `let myCoords: intCoords = (10, 10, 10)`
* Types, if not using the type keyword, are inferred for us.

## Destructuring

* ex: `let someInts = (10, 20); let (myFirst, mySecond) = someInts;`
* Can lead to type annotations:
  * ex: `let (ten: int, twenty: int) = someInts`
* Heavily used to avoid the use of intermediate variables.

## Pattern Matching

* Used to make sure a program complies with all possible use cases:
    ```
    type response =
    | Good(string)
    | Bad(int)
    | Waiting

    let data = Good("you did it");
    let message = 
      switch data {
      | Good(message) => "We are excited" ++ message
      | Bad(errorCode) => "Woops, error found: " ++ errorCode
      };
    ```
* The above will throw an error because not all patterns were taken into consideration.
* A special unmatched case is always available using the `_` operator.
  * kind of like a fall through case.
* The `when` keyword is used as `if` statement sugar in a pattern match:
  * ex: `|Bad(code) => when stausCheck(code) => ...`
  * this shouldn't be overused though.
* Exceptions can be used throughout this process by using the `exception exception_name` pattern.
* Throughout, this will be way more performant than if/elses.

## Data Structures

### Variant!

* ex: 
    ```
    type myResponse = 
    | Yes
    | No
    | Always
    ```
* These values above are known as 'constructors' or tags.
* Each variant's constructors need to be defined using capital case
* These structures lean heavily on the switch statement:
    ```
    let message =
    switch myResponse {
    | No => 'Good luck'
    | Yes => 'Keep it up'
    | Always => 'Chamon, push yourself'
    }
    ```
* Variant's can tell the programmer if a condition hasn't been thought of.
* They can also can detect if a branch is redundant and removable (refactorability).
* Variants can hold extra bit's of data:
    ```
    type account =
    | None
    | Twitter(string)
    | Facebook(string, int)
    ```

### Record

* Very similiar to a JS object.
  * Much faster, immutable, and typed
* ex:
    ```
    type person = {
      age: int,
      name: string
    };
    ```
* use:
    ```
    let dad = {
      age: 50,
      name: "Pops"
    };
    ```
* Dot notation is used to access items in a record.
* Like in Elm, these will be written/listed in a type file.
  * These files are often times capitalized names for the types within.
  * ex: `School.re` will define a `type teacher...` and a `type professor...`
  * using these type files to define a new object: `let me: School.professor = { age: 50, classes: ... }`
* Since all records are immutable we need to create new ones when we alter a value.
  * the spread operator helps us here: `let newMe = { ...me, age: me.age + 1 }`
  * The `mutable` keword can be used when defining a type to get around this.

### Tuple

* Like a record (immutable) but, ordered, and fix sized.
* ex: `let myTuple = ("10", 29, 38, "ME")`
* Tuples are often used locally and not long lived.

### List

* Must contain all of the same type and are still immutable.
* They are however, extremely fast at prepending and splitting.
* The efficency of lists is done by sharing information between two lists:
    ```
    let listOne = [1,2,3];
    let listTwo = [0, ..listOne];
    ```
* In the above listTwo resolves to: `[0,1,2,3]` but references the last three items.
* There are quite a few functions available to access specific values using the List lib.
* Switches + pattern matching are usable when cycling through a list:
    ```
    let message =
      switch myList {
      | [] => "Empty"
      | [a, ...rest] => "The first item in the list is" ++ a
      };
    ```

### Array

* Arrays are very much like lists but, are mutable and faster at random access/writes.
* The difference when defining them: `[|1, 2|]`
* Accessing arrays is very much like JS: `myArr[0]` to get a specific item.

[cht]: https://reasonml.github.io/guide/javascript/syntax-cheatsheet
