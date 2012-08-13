* Useful instead of the good ole if/else malarkey when trying to build in some kind of exception handler.
* Syntax looks like this:

```javascript
try {
  // Try and do something fun
} catch (exception) {
  // do something
} finally {
  // do something to wrap up because we are done
}
```

* Anything in the finally block gets executed no matter what.
* `throw` can also be used to throw an object, string, number or a fit if something goes wrong.