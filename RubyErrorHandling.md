* [Ensure Clause][0]
* [Retry Clause][1]
* Strait [Raising Exceptions][2]
* [Catch-Throw Errors][3]

###Method Missing

* We are free to define `method_missing` in any way we feel fit, just the way we define any method.
* Input params for the method are usually: `method_name` followed by a sponge var named `args`

###Constant Missing

* Identical to `method_missing` except it throws errors when a constant is unknown or MIA
* Constants don't take arguments so the `const_missing` method will only take one argument itself (name)
* Needs to be a class method (`self.const_missing(cons_name)`)



[0]: /EnsureClause
[1]: /RetryClause
[2]: /RaisingExceptions
[3]: /CatchThrowErrors