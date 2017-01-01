# Ruby Logic

## Notes

* Most of these are methods that are implemented on `Kernel`

## Flow control

* [For Loops][1]
* `If` and there opposite brothers the `Unless`
* `While` and there opposite brothers the `Until`
  * Can be composed to do some powerfully concise things:
  * ex: `perform_stuff() until finished?` or `perform_stuff() while not finished?`
  * the `redo` method can also be used here, jumping back to the beginning of loop body.
* `Times` is used to do something `n.times`.
* `Upto(n)` is somewhat like `times`.
  * ex: `0.upto(7) do |I| ; puts I ; end`
* `Begin` can be used as well as a bit of flow control
  * [Example][2]
* Ruby's case statement is almost a direct lift from Pascals.

[1]: /RubyForLoops
[2]: /RubyBeginFlowControlExample