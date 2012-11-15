An assignment statement sets the variable on the left side (lvalue) to refer to the value on the right (rvalue).

* If ruby sees a comma separated list for rvalues then it kicks into parallel assignment mode.
  * it then looks at all lvalues and if it sees a coma it assigns the correct amount of variables and pitches the extras
* Asterisks(*) absorb values.
  * if a rvalue array or set has an asterisk then it will evaluate the array before assigning values to the left side.
  * if a lvalue contains an asterisk it soaks up remaining values from the right side
* lvalues may contain a parenthesized list of terms
  * This forces ruby to extract the corresponding rvalues, assign it to the terms, and continue onto the higher levels.
* defined? returns nil if the argument is undefined and a description if it is
* {{RubyGettersSetters}}