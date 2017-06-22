# Ruby Debugging

## Notes

* Get a list of named params passed to a method (if in the method scope): `method(__method__).parameters`
  * to get the actual items passed in use: `binding.local_variable_get(:keyFromPrevious)`
* pass `-r debug` into the terminal when running ruby and a file name to initiate the debug menu
* `-w` flag will initiate warnings if and when they come up
* {{RubyPerformance}} issues can be put under a microscope and evaluated to solve issues