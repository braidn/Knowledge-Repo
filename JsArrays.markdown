###Methods

* access to both `.pop` and `.push` methods just like ruby.
* `.splits` and `.joins` work much like ruby as well
* `.slice(startNumber, endNumber)` will extract the words.
  * also used to copy an array from one variable to another
    * if done with simple `=` it is a pointer, not a copy
* `delete myArray[0];`
* `.unshift` is the opposite of push meaning the value goes to the beginning of the array
  * unshift works the same but with pop
  * unshift is much slower to use than push
* `.concats` basically flattens multi dimensional arrays

###Looping

* `.length()`1 method is handy for finding the overal length of an array
* `arrayName[indexNumber]` will output whatever is at that specific point in the array
* It is better resource wise to set a variable to the array length and compare the iteration to it
  * `for(var i = 0; count = array.length, i < count; i++){}`
* if the space in the array is undefined:
  * `if(myArray[i] !== undefined {do something}`
* [For...in looping][1] is also available
  * the return will not be in any specific order
  * very slow, used when no other loop is available

###Strings

* string are basically just groups of arrays
  * this means we can grab characters out of a string with an array index

###Dimensions

* The idea of an array in an array...so fucking Inception
* To access these values: `arrayName[0][0]`

###Associative

* Think about [ruby hashes][0]
* `var myHash = {key1: val1, key2: val2}`
* looping over these arrays is really easy with the [`for in` array][1]


[0]: /RubyArrays
[1]: /JsForInLoopExample