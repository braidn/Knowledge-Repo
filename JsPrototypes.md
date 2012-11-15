when creating a function for an object:

    buddy.bark = function() {
    console.log("do something");
    };

like above, it will only fire for that specific object. Not the whole class. To fix this use the prototype operator.

    class.prototype.bark = function() {
      console.log("Woof");
    }

now all class of dogs know how to bark