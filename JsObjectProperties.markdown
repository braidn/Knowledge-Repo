* All properties assigned to an object are automatically public.
* If a property within ab object is defined without a `this` and with a standard `var` then it is considered Private

      function Bankaccount(name) {
        this.name = name;
        var account = 4500;
      }

* This can be circumvented by declaring a public function for the object that returns the variable.
  * It is also possible to use this same idea when returning private methods.
  * Also remember that it is responding with a method that __ISNT__ automatically going to be called, you will need to call it using ().
    * Example: `console.log(objectName.methodName());`