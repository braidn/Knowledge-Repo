flash is basically a temporary key => value store scratchpad

* It holds instance variables and values in storage for ONE redirect, then dumps them
  * So A knows about B; however C knows about B but NOT about A.
* Most commonly used for storing error messages or general status updates
* A call to `flash.now` will updates the current flash but puts nothing into sessions
* `flash.keep` will force entries to stick around for the next request cycle.
  * If no params are passed, everything is kept...greedy little bastards