# Rust Programming Language

## Notes

* Constants are immutable always, can't be the result of a func return, and must have type defs.
* Considered an expression based language.
  * meaning most statements return code.
* `new` is a convention used to define constructor functions.

## Cargo

* A lot like bundler but able to run programs as well.
* `cargo run` : compiles and runs the code in a cargo inited directory.

## Functions

* Can be nested in other functions to accomplish a bit of namespacing.
  * These inner functions have scoped data rules as well.

## Implementations

* Methods can be implemnted on enums/structs, etc.
  * This is kind of like duck typing in Ruby, kinda not.
* Use the `impl` keyword and create a named function to create these inherent implementations.

## Macros

* Denoted by a `!`

## Types

* Really encouraged to think about the type of all args along with the type of the return.
* Generics datypes are availble within the langueage with the very commonly used: `<T>`
  * Enums/Structs can take utilize this to create a sense of polymorphism.
  * Another word for these are 'option types' and it's also supported in the stdlib.

### Traits

* Properties that Types must uphold, can be thought of as traits.
* These are defined very much like enums/structs.
  ex: `pub trait Minimum : Copy {}`
* These are passed before function arguments and are called 'trait bounds'.

## Patterns

### Immutability

* Immutability is all throughout the language and programmers encouraged to use it liberally.
  * This means things like variables are immutable by default (use `mut` to de immutable them).
* When a variable changes value due to it being reset by `let`, it's called 'shadowing'.
* Shadowing allows for reassignment of types where `mut` values must retain the same type.
