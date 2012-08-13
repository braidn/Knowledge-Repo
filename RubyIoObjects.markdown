A bidirectional channel connecting a Ruby program with some form of external source

* The `File.open` action is closely related with IO objects
* When using `File.open` a good rule of thumb is to use `File.close` when all actions are finished with the specific file
  * A way to get around this would be to open the file in a `block`. As the block hits the `end` it auto-magically is closed.
    * {{RubyFileBlockExample}}
* {{ReadingFromFile}}
* {{WritingToFile}}
* {{RubyIoNetworks}}
* {{StringIo}}