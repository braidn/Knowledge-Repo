* Arguments passed to ruby do/end block during step definition
* Created by surrounding an item with parenthesis
* Use a pipe character(|) to separate different used values but use the same argument
* The period can also be used to match any single character
  * it is totally legit to match any three characters with == `..`
  * star characters(*) are also totally legit `.*` == find any character any number of times
* Ranges are also totally usable with: `([0-9])`
  * or just the digit regex tool: `\d`
* A step can have any amount of capture groups as needed.
* `^` is used to anchor the expression at the beginning
  * `$` does the same but at the very end

###Non Capture

* Sort of a way to write one step that matches several different phrases
* Written much like the capture group but with a pipe like: (?: stuff | stiff)
* Creates _NO_ argument group