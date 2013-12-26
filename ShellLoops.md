##Notes

* For loop: 

```
for var in list;
do
  commands;
done
```

* Loops can be fed by ranges: `{1..50}` which are very ruby like
  * `for i in {a..z}; do actions; done;`
* While loop:

```
while condition
do
  commands;
done
```

* Until loop:

```
until [ $x -eq 9 ]
do
  let x++, echo $x;
done
```
