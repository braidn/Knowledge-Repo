# Ruby Enumerables

## Notes

* to start call `include Enumerable` within a class
  * __Make Sure__ that you have an `each` method defined somewhere in the class
* All in all, the Enumerable call adds around 40 different methods to a class

## Ranges

* Ranges are inclusive/exclusive of their ending value.
  * An inclusive range or a 'closed range' will include it's last value.
  * The opposite is true for open ranges: They don't include their final value.
* Ranges are really built to be iterated over.
  * They have `#succ`, `#begin` and `#end` methods which make iteration a breeze.
* Flip-flop operator: `..`
  * Used to define a Range.
  * Each time items are evaluated, the whole range is re-evaluated (especially both ends).
    * This means that both ends of a range are basically procs (they are code VS values).
