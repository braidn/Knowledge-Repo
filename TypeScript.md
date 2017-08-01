# TypeScript
[[_TOC_]]

## Notes

* Types, like in most modern type based languages, are optional and inferred by the compiler.
* ALMOST always a `tsconfig.json` config file is required in the root directory of the project.
 * [docs for the tsconfig file][1]
* A glob param can be used. This is much like Ruby and will process the param as an array.
  * ex: `function manyParams(param1, param2, ...allTheRest) { console.log(allTheRest) }`
* Tagged templates are a great way to build functions that pre process string literals.
* The spread operator or `...someList` is totally usable throughout TS.
* `Bind` is pretty harmful since it always returns an any.
* Currying can be achieved with ease by chaining fat arrows:
  * ex: `let add = (x: number) => (y: number) => x + y;`

## Interfaces

* TS only sugar that's parsed out of the file during the compile process. Dev only.
* These are then passed as type definitions to functions as params.
* Usually Plain Ole Javascript Objects that abide by the interface.
* ex: 
```
interface Food {
  name: string;
  cals: number;
}
```

## Classes

* Type system somewhat similar to JAVA/C#
  * also quite similar to ECMA2015 but, much more strict over the pure JS implementations.
* Start by listing the **properties** of the class much like the interface.
  * by default these are public and accessible using the `this` keyword but, can be private/ protected.
* `constructor` function is used when 'initing' the class.
  * when extending a class, a new `constructor` or redefined one is required.
  * however, properties and methods come over into the extended classes.
  * a `super(params)` method is available to call the constructor on the extended class.
  * super must be used when extending a class. TypeScript will warn you if this doesn't occur.
* Because property declaration and setting is so common it can be shorthanded in the constructor:
  * `constructor(public x:number) { }`
  * this allows the class to set x on instantiation and axxess it using `this.x`
* Classes while poo pooed by most JS devs, are really quite useful and create well thought out wrappers around functions.

###Subclassing

* Like many OO based languages, TS has private, public and protected properties
* Member properties are not accessed in child classes using `super`.
  * Instead, `this.property` is used.
* Due to `this` being the context of the function invocation, using `this` to access parent methods can be weird.
  * Problems here can be mitigated by creating a copy of the parent method before overriding it.
  * It's very similiar how one used to capture context using `_self = this`.

###Statics

* Static properties are shared across all instances of a class.
* They act very much like singletons.
* Created using the `static` keyword and accessed like all other properties.

## Destructuring

* Works very similiar to other languages:
  * ex: `let tangle = { x: 0, y: 10, width: 5 }; let { x, y, width } = tangle`
  * variables x, y, and width are now set.
* Deep destructuring is also completely valid:
  * ex: `let foo = { bar: { baz: 10 } }; let { bar: { baz } } = foo`
  * baz is now set and available.
* Array destructuring is also completely doable:
  * ex: `[x, y] = [ y, x ]`
  * using the splat op: `...theRest`, you can assign the remainder of the array to a new array
  * ignoring an index is completely doable by leaving the item empty when using destructuring.

## Generics

* Templates that allow the same functions to receive different types.
* These preserve the type of data/vars that flow in and out of them.
  * ex `function genericArrCreator<T>(argument: T): T[] {}`
  * to use: `var genericNumbArr = genericArrCreator<number>(23)`
  * the `T` var above can be anything but T for 'type' makes sense
* Explicit 'return' values are required/helpful in Generics.
* Providing a type in the generic function call isn't required but, good practice.

## Modules

* Commonly using the `export` keyword will create a namespace.
  * This means that `import` can be used to pull modules into other files.
* These are not built in but, hook into external libraries.
* For the browser, require.js is used and
* For the server, CommonJS is used
* Lot's of issues here might be cleaned up by TypeScript 2.0

## Namespacing

* TS offers the `namespace` keyword to contain a logical group of functions.
  * ex: `namespace Utility { export function someFunc(someParams) }`
  * the above could be called using: `Utility.log('hello')`
* Namespacing can be nested allowing for all kinds of buckets.

## Enums

* A way to organize related values.
* Seen in C# and Java but not really in JS/Ruby
* All TypeScript enums are number based
  * By default the numbering begins at 0 and increments by 1 (normal array)
  * assignment is allowed in the definition though and allows and enum value any valid number
* Can be made as constants usign the `const` keyword before `enum`

## Guard Types

* Types used to guard control logic from firing if not `typeof` some defined type.
* These types are often user defined.
  * but can be `typeof` or `instanceof` but can be of type `null` or `undefined`
* Null and undefined checks need to be setup through the `--strictNullChecks` flag
  * otherwise they are considered valid values for __all__ types.
* These are also aware of the `if` and `else` JS syntax.
  * This means that if we are typechecking in an else block, 
  it know's what params are required due to comparing against the if condition

## Async/Await

* This has been available for es6 targets since 1.7
  * es5/es3 was added in TS 2.1

## Third Party Interops

* To do this, a declaration file will need to be written and suffixed with `.d.ts`
* Many of these already exist for popular projects at [DefinitelyTyped][2] and [Typings][3]

## Types

* Either created using interfaces or the `type` keyword
  * example: `type StrNumb = string|number`
* Type aliases can be created wherever and are preferable when using simpler objects.
* Optional params can be marked by adding a `?` to the end of the param's name
  * what's cool is this means we can also add default values in much the same way: `bas : string = 'hello'`
  * and because types are building documentation, we can use method overloading with optional params.

### Common Types

* **Number** – All numeric values are represented by the number type, there aren’t separate definitions for integers, floats or others.
* **String** – The text type, just like in vanilla JS strings can be surrounded by ‘single quotes’ or “double quotes”.
* **Boolean** – true or false, using 0 and 1 will cause a compilation error.
* **Any** – A variable with this type can have it’s value set to a string, number, or anything else.
* **Arrays** – Has two possible syntaxes: my_arr: number[]; or my_arr: Array<number>.
* **Void** – Used on function that don’t return anything.

### Union Types

* Denoted using the `|` operator.
* Used to denote the types that are allowed to a param/func.
  * Handy if your function can take a single item or array of items.

### Intersection Type

* Handy when using `extend` to smash two objects together.
* This type is written like: `function something<T, U>(first: T, second: U) {}`
* Lots of safety here especially when using several intersecting interfaces.

### Tuple Type

* JS has no knowledge of tuples however, this type hacks it under the hood using arrays.
  * example: `let myTuple: [string, number]; myTuple = ['braden', '22']`
* Handy, especially when thinking about destructuring.
  * `let [name, age] = myTuple`

### Method Overloading

* More for documentation anything.
* All possible params to the function are defined in the func header with no func block
* The last or fallthrough func definition contains the func block that will fire for all of the func defined as 'headers'
* There is also _no runtime overhead_ to overloaded funcs, it's all for the compiler

### Literal Types

* ex: `let bar: 'Hello'`
  * in the above, the variable bar can only ever be assigned to the string Hello.
* This is super powerful when combining with type unions because it creates a list of accepted values passable to the func.
* Boolean and numbers can be used in this same fashion.

### Readonly

* Properties throughout any interface and class can be marked as `readonly`
  * ex: `config: { readonly stripe_key: string }`
* These readonly attributes are immune (blocked by the interpreter) from being mutated.
  * In a kind of way this is a bit of free immutability without another library. 
* TS has a built in interface for Arrays called: `ReadonlyArray<T>` which will automatically create read only arrays

### Never Type

* A base case, or sometimes called a bottom case.
* Fails or error throwing is also considered an error case.
* Void and Never are somewhat different:
  * Void is a unit where Never is a falsesum
  * A function that returns nothing will always be a Void.

[1]: http://www.typescriptlang.org/docs/handbook/tsconfig-json.html
[2]: http://definitelytyped.org/
[3]: https://github.com/typings/typings
