Think of it on the lines of a bathroom hall pass. The student must return from the room before another is to be allowed to go.

* if a mutex is locked, threads will pause (wait) until they can have access to it to continue their routines
* kind of built like do blocks but instead of utilize this {{MutexSyntax}}
  * you can also pass a `mutex.syncronize` block and it will always exit no matter what.