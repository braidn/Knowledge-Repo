* Used to dry up steps
* Responsible for converting a specific capture string into something a bit more meaningful

Syntax:

```
Transform /^\d+$/ do |numb|  
  number.to_i  
end
```

* When a step definition is run it checks for any transforms that match each argument
* if a transform match is found then the found set gets passed to the transform, shit is done, then yielded back to the step
* Constants can be used to capture result from transform and the constant passed to the step rather than the Regexp