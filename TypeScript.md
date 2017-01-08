# TypeScript

## Notes

* Types, like in most modern type based languages, are optional and inferred by the compiler.
* ALMOST always a `tsconfig.json` config file is required in the root directory of the project.
 * [docs for the tsconfig file][1]

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

## Common Types

* Number – All numeric values are represented by the number type, there aren’t separate definitions for integers, floats or others.
* String – The text type, just like in vanilla JS strings can be surrounded by ‘single quotes’ or “double quotes”.
* Boolean – true or false, using 0 and 1 will cause a compilation error.
* Any – A variable with this type can have it’s value set to a string, number, or anything else.
* Arrays – Has two possible syntaxes: my_arr: number[]; or my_arr: Array<number>.
* Void – Used on function that don’t return anything.

[1]: http://www.typescriptlang.org/docs/handbook/tsconfig-json.html