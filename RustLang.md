# Rust Programming Language

## Notes

* Constants are immutable always, can't be the result of a func return, and must have type defs.

## Cargo

* A lot like bundler but able to run programs as well.
* `cargo run` : compiles and runs the code in a cargo inited directory.

## Patterns

### Immutability

* Immutability is all throughout the language and programmers encouraged to use it liberally.
  * This means things like variables are immutable by default (use `mut` to de immutable them).
* When a variable changes value due to it being reset by `let`, it's called 'shadowing'.
* Shadowing allows for reassignment of types where `mut` values must retain the same type.
