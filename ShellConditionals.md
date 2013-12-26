##Notes

* If condition:

```
if condition;
then
  commands;
fi
```

* If/else conditions:

```
if condition;
then
  commands;
else if conditions; then
  commands;
else
  commands
fi
```

###Comparison Operators

* `-eq`: equals
* `-ne`: not equals
* `-gt`: greater than
* `-lt`: less than
* `-ge`: greater than or equal to
* `-le`: less than or equal to
* `-a`: and used like `[ $var1 -ge $var2 -a 2 ]`
* `-o`: or

###String Comparisons

* Best practice is to use double quotes to avoid errors
* `-z` to find if a variable holds an empty string
  * `-n` opposite, will return true if a nonempty string is found
