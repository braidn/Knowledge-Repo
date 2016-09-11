# JavaScript Promises

## Notes

* Async JS pattern that allows you to write less right leaning code.
* Control flow is used by chaining `then` and `catch` functions.

## Examples

* A setTimeout function could be written:
```
function sleep(time) {
  return new Promise((resolve) => setTimeout(resolve, time));
}
```