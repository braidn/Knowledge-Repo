Think of constants as files at the end of a file tree. Like the file tree, you can have identical file names as long as they live in different trees.

* You can also specify the path to a constant with: `My Module::My Class::My Constant` < pretty friggin awesome!
* A container of constants is often called a {{RubyNamespace}}
* When including files, be aware that they bring along their own constant namespaces that can pollute your own.
  * Bypass this little issue with `load('fileName.rb', true)`