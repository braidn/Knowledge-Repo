Tied to a class and not a method, built by initiating the dreaded `@@`

###Facts

* not visible to the outside world
* when you call or reference a class variable, Ruby looks in the current class first, then up the iTree to find it.
  * if it fails to find one, it will simply create it in the current class
* Considered vertical global variables
  * restricted to a single inheritance tree and global within it.