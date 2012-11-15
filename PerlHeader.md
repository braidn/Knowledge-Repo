###Notes

* Most of the time written WITHOUT a specific extension
* Run with the common `./` syntax
* Best practice is to run `which perl` and then use the output with the
`#!` syntax at the top of the file so it knows what environment to use.
* The [pragma][2] `use warnings;` will enable warnings for syntax
errors.
* User input is best grabbed by STDIN and is easy by calling `<STDIN>;`
* `chomp($some_var)` function is super handy for cutting off the trailing newline
in input text

###Numbers

* Perl computes with double-precision floating-point values
* Whole numbers can be broken up with `_` in place of commas to make
things more readable
* Numeric operators are pretty much standard ([Modulo][1] is include)

###Strings

* An `empty string` is considered a string
* Because Perl is aging, utf-8 use must be declared with `use utf-8;`
* Double quoted string will interpret variables
* Concatenation is done with the `.` operator __NOT__ `+`
* Perl has a string repitition operator = `x` that allows you to
multiply strings by the following number

###Variables

* Always start with a Sigil(`$`) or "single item" and can't start with a number
* Names are case sensitive therefore `Tim` and `tim` would be different
* If adding items to a variable (`$tim = $tim + 3`) using the shorthand
(`$tim += 5`) is valid. Using the string concatinator(`.=`) this way is also
valid.
* Printing of variables(`prints`) can be invoked over any items by
seperating them with a `,`(`prints $awesome, $time, $call`)

###Falsey V True

* 0 is false, with all other numbers being true
* Empty strings are false, and all others _besides_ "0" are true

###Control Structures

* `keyword (item) { stuff; }`
* Often times it is a good move to keep things indented and looking
pretty (like all languages)
* If statement: `if (5 > $something) { stuff } else { something else }`
* 


[1]: https://en.wikipedia.org/wiki/Modulo_operation
[2]: http://www.cs.cf.ac.uk/Dave/PERL/node138.html
