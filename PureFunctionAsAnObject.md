# Pure Function As An Object.

## Notes.

Ruby specific pattern that compromises:

1. creates an object of its own class,
1. passing its argument into the initializer,
1. and calls a single method on the object, to generate the return value.

Most of the functions will have 0 side affects (how we can sorta call it pure)
