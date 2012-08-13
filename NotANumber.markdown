basically a number that Javascript can't parse as a number. A pretty colossal fuckup

* this is false: `NaN === NaN`
* this is a little odd: `typeof(NaN) = 'number'`
* To be sure a number is actually a number use `isNaN(number);`