* `!` to clear the buffer
* `cd` into models
* `nexting` command shows you where you are and `exit` bumps you up
* `use -h` along with an item for a list of commands
* `show-input` will read you back where you are in the class or method\
  * this will also print out a series of lines items are on
  * if you fucked up for some reason you can use `amend-line N newCode` where N is the number of the line
* `show-doc` is used with an item to see the documentation for the specific object
* `show-method` to find some source code
  * `edit-method methodname` will open an editor and take you to the methodLine
* prepend commands with . to perform system commands
* If you add in `binding.pry` into your method call you build a brakepoint in the method
  * This is completely kick ass for debugging
* If pry is installed in the gemfile you can add a `binding.pry` call to the views.
  * This will add the ability to cause a brakepoint when `rails s` is called in the terminal.
    * Use `exit-all` to continue the load process