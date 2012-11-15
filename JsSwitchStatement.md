basic syntax which is a little different than Ruby:

    switch(stuff/var/etc) {
      case "something":
      result = "awesome";
      break;
      
      default:
       result = "boring";
    }

* Also great for creating fallthroughs
  * multiple case statements have the same resulting statement
  * this is accomplished by omitting the `break;` statements