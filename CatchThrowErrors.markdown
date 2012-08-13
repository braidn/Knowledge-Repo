* `catch` defines a block with a symbol `catch (:symbol)` and is executed until it finds the corresponding `throw :symbol`
  * catch blocks are generally `do` blocks
* Throw zips back up the list and looks for the corresponding symbol and executes it's test (unless, if, etc). If it doesn't find it, it breaks, catch returns nil
* throw DOES NOT have to fall in the scope of the catch block.