##Notes

* Range from mathematical to bitwise based operators

###Unary

* Most common being `++` and `--` used to increment and decrement a
number by 1
  * These can be placed prefix(`--someNumb`) and postfix(`someNumb--`)
  and will have somewhat different numbers
  * If in postfix, the entire equation is fired, meaning `--22 + 1 = 22`
  and `22-- + 1 = 23`, kinda confusing
* Sometimes `+` is used to create a number: `+someNotNumber` and the
result would be a number (if it could be converted successfully,
otherwise just `NaN`)

###Bitwise

* All numbers in ECMA are stored as 64 bits
  * However, bitwise ops can't work with 64bit numbers so the numbers
  are moved to 32bit, modified via bitwise, than turned back into 64bit.
  * All of this is pretty seamless but good to know
