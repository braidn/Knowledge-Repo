Hash tables are pretty cool, they trump Arrays in a few interesting ways.

* Arrays need to look up things by numbers and they look through the entire index every time.
  * This means out of 10 values the average lookup path will traverse 5 objects
* Hash tables go around this issue by splitting things into buckets and looking up items through each bucket.
  * so, to take the example above, you might split things into 5 chunks of 2, therefore finding something on the first or second try
* Pretty cool