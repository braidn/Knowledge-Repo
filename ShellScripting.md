##Notes

* `set -e` is a good thing to use because if any part of the script fails than 
it won't continue and will roll back the entire script
* creating or rewriting a whole file can be done with `echo 'something' > stuff.txt`
* appending can be done by `echo 'something' >> someExisting.txt`
* use -x flag to enable debug tracing to shell scripts.
  * also `-xv` can be added to the shebang to set debugging on
* `$?` to access exit status (usually 0 if successfull)
* [Field Seperators and Iterators][1]
* [Loop][2]
* [Comparisons and flow control][3]

###Args

* `$1, $2` used to access argument 1 and 2 
* `$@` print all args at once
* `$*` print all args in one string (entity)

###Variables

* `var=something` and `var = something` are completely different
* Printing variables is done by prefixing `$` to the var name
* `let` can be used to perform basic ops on vars directly
  * `let var1++`
  * this: `$[var1 + var 2]` is a also an alternative to `let`

###Standards (error/input/output)

* 0 = stdin / 1 = stdout / 2 = stderr
* these can be redirected to files: `echo 'fart' 2> someError.txt`
* stderr output is dumped to /dev/null

###Arrays

* Bash supports associative and traditional (numerical indexed) arrays
  * associative is fairly new, introduced in 4.0
* To print all values in an array: `array_1[*]` or `array_1[@]`
* To print a list of indexes: `!array_1[*]`

[1]: /ShellIFS
[2]: /ShellLoops
[3]: /ShellConditionals
