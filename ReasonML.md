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
* The Bucklescript compiler is super smart and will remove unused code where needed.
  * It will also inline function invocation if it can decern the output.
  * All of this makes for heavy optimization in the JS output.
* Reason ships with a REPL so testing ideas/code is as easy as IRB.
  * to start it: `rtop`
  * this is a great way to play with the language, think irb for Ruby.
* Most of the language and programs is lexical scoped.
  * this really applies to let bindings within a specific scope.
  * this also means that using blocks to create local scope is a big concept, like Ruby.
  * Scope like this is created by encapsulating logic in `{}`
* Structural comparativeness runs pretty deep in the language.
  * ex: `(true, [{name: "bob", city: "toronto"}]) == (true, [{name: "bob", city: "toronto"}]);`
  * most folks use this throughout the language because it's resource wise cheaper.
* Referential comparing is done just like in JS using the threequal operator: `===`
* References to objects are created by: `let foo = ref(someValue);`
  * to change this value: `foo := 8;`
  * to access this value: `foo^;`
  * these are particularly handy in storing global references that can be passed around/changed over time.
  * Use sparringly!

## Functions

* Functions are defined like es6 fat arrow functions.
* They can be either single line:
  * `let someFunc = (name) => "Hellow" ++ name`
  * or multiple lined using the block syntax
* If a func has a single param and is defined by an identifier,
  the parenthesis around the param can be omitted.
* Mutually recursive functions are defined using the `and` keyword
* There is no need for an explicit return in a function.
* There are no nullary functions in the language.
  * The compiler will add a `unit` to a null func if defined.
  * The reason here is Reason returns partial applications, much like Elm.
* Some function signature rules:
  * If a function has a single primary parameter,
    make it a positional parameter and put it at the end.
    That supports the pipe operator for function composition.
  * Some functions have multiple primary parameters that are all similar.
    Turn these into multiple positional parameters at the end.
    An example would be a function that concatenates two lists into a single list.
    In that case, both positional parameters are lists.
  * All other parameters should be labeled.
  * If there are two or more primary parameters that are different, all of them should be labeled.
  * If a function has only a single parameter, it tends to be unlabeled, even if it is not strictly primary.

### Arguments

* Reason _enforces_ arguments to every function.
* If a function doesn't require a argument, a unit: `()` is passed instead.
* Only labeled arguments can have a default value `...(~lastName="douglass", ...)`
* Arguments can be labeled if needed.
  * ex (called 'punning sugar'): `let mapCoordinates = (~y, ~x) => ...`
  * when calling: `mapCoordinates(~x=44, ~y=34)`
  * with named arguments we can reorder them as needed or whichever makes sense.
  * this can be made further explicit: `let mapCoordinates = (~lat as x: int, ...) => ...`
  * The function will be called with the lat name and the block will utilize the x name
* Currying is completely built in.
  * Any function can be curried and this currying is optimized by the language.
  * The return of the original function is a function that can be applied.
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
* Type variables is a way for a type to take a generic type and have it remain throughout the type def.
  * these are usually parameters to a type def: `type myRadio('a)`
* Option values allow the use of the `None` type which can be thought of as a Null/Nil elsewhere.
  * these are defined by: `option('a)`
  * errors are also prefixed specially by: `result('a)`
* Types are often times composed together.
* If a dev wanted, they could shadow a previously defined type with a new type.
  * This is somewhat confusing but shows the power of the type system.

## Destructuring

* ex: `let someInts = (10, 20); let (myFirst, mySecond) = someInts;`
* Can lead to type annotations:
  * ex: `let (ten: int, twenty: int) = someInts`
* Heavily used to avoid the use of intermediate variables.

## Pattern Matching

* Performs two operations:
  * matches on a specific use case or cases.
  * extracts part of the match and passes it to the result or return of the match.
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
* We can assign matches to variables and use the variables in the response to the match.
  * `head` and `...tail` can be used when pattern matching lists
* Arrays can only be matched on their specific length.
* Records can match exact values.
  * and using puning, we can capture the record item's value and pass it through to the match.
* The `|` character can be used to match multiple cases to the same result:
  * ex: `| 1 | 2 | 3 => "These are valid numbers"`
  * this is also usable when matching on types:
    * ex: `| Error(500 | 501 | 502) => "Errors encountered"`

## Modules

* Module
  * CapitalCamelCase is also the default for naming (somewhat different than other langugaes).
  * Submodules are usually defined in the scope of these file level modules.
* Much like in every other language: Modules are a way to namespace and encapsulate code functunality.
* One large Reason pattern is to have a main type per module with the name `t`
  * ex: `SomeModule.t.someMethodOrVar`
* Sometimes/often there is a make function that sets up the module at runtime.
  * this is not a Reason pattern but, an Ocaml one.
  * also often called 'initialization' where a new version of something is created (OO baby!)
* To pass these around we use the `open` keyword followed by the module namespace.
  * This pulls all values from the module into the current scope (where `open`) was invoked.
  * this can also be done using: `School.(SomethingInSchool => "Scopeing achieved!");`
  * this is often times called 'local opening' and is often times the safest way of opening a module.
* Sometimes you want to pull modules in locally to avoid name clashes.
  * ex: `let () = Log.(make() |> someLogFn("Hellow"))`
* Sometimes these are encapsulated in an immediate invoking unit:
  * ex: `let () => { print_string("Hello World!") };`
* There is even the `include` keyword to pull modules into specific scopes.
  * this has a very similiar type of action to Ruby's module `include`.
  * even Interfaces can be included in one another (drastically easing on the code duplication)

## Interfaces

* Control what what or how much is exported from Modules or `re` files.
* Usually named the same/in the same dir as the module but ends with a `rei` extension
  * These are patterns set forth in Ocaml.
* Sometimes these files are also called 'signatures'
* Each item in this file is a type signature: `let times: (int, int) => int;`
  * Any signatue defined in this file will be automatically exported.
  * This means leaving anything out of these files will omit them from being exported (IE hidden)
* Bucklescript has the ability to auto generate these files for us (if we are lazy)
* Interfaces can include modules indirectly if an interface is not availble for named inclusion
  * ex: `include (module type of Log);`
  * The trick here being any module that is of the above type will need to include module `Log`

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
  * the term tags is used because in CS this is known as 'tag unions'.
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
* These can even be polymorphic which is more of a way to extend or compose variants.
  * this allows the programmer to build complex, and powerful type hierarchies.
* Although polymorphic variants are usable, they aren't as strict as regular variants.
  * due to this, it's highly recommended to reach for polymorphic variants only when absolutely needed.
* Variant's can tell the programmer if a condition hasn't been thought of.
* They can also can detect if a branch is redundant and removable (refactorability).
* Variants can hold extra bit's of data:
  ```
  type account =
  | None
  | Twitter(string)
  | Facebook(string, int)
  ```
  * when pattern matching these variants with extra data, we can pass types or specific items.
* Reason also uses `None` and `Some(value/values)` to get around the concept of Null in varaiants.

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
    * ex: `lion = { mutable scary: bool }`

### Object

* Looks very much like a record but has a dot(`.`) at the beginning:
  * ex: `type toots{. position: integer};`
* If a single dot is placed at the beginning, the object is 'closed'
  * This simply means that any object based on this type must have _the same_ structure.
* Objects can have two dot's (known as an 'elision').
  * This denotes the object as open/polymorphic/or can contain other values.
* May contain a `this` keyword which, unlike JS, points to the current object correctly.
* Bucklescript also has a special object type that's different than Reasons (confusing).

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
    | [a(head), ...rest] => "The first item in the list is" ++ a
    };
  ```
* Use the `@` operator to concatentate two lists together.

### Array

* Arrays are very much like lists but, are mutable and faster at random access/writes.
* The difference when defining them: `[|1, 2|]`
* Accessing arrays is very much like JS: `myArr[0]` to get a specific item.
* There are quite a few StdLib functions available on `Array`

## Exceptions

* Like everything they can be pattern matched.
* Often times though the `Not_Found` is thrown.
* Use sparringly!

[cht]: https://reasonml.github.io/guide/javascript/syntax-cheatsheet
