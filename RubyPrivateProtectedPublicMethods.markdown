* all instance methods are public by default
* two different ways to set methods to private or protected
  * adding `private` before the method definition
    * {{RubyPrivateMethodExample1}}
  * making them private after the fact
    * {{RubyPrivateMethodExample2}}
* private methods can't be called from object reference ( `n = doc.word_count` )
  * instead they are called from within other public instance methods
* the `.send(:method_name)` method negates all visibility rules and allows the method to fire
  * acts as an override of sorts when in need (puts the power into the hands of the programmer)