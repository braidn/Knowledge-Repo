# JavaScript Promises

## Notes

* Async JS pattern that allows you to write less right leaning code.
* Always in a state of resolved or rejected.
* Control flow is used by chaining `then` and `catch` functions.
* Map/Reduce functions are syncronous which means the promise's are unable to resolve until called.
  * A good way to return a collection of them: `await Promise.all(arrayOfPromises)`

## Async/Await

* These patters derive from there implementation in C# and F#.
  * Looking up issues
* This feature relies heavily on _all_ functions returning a Promise.
  * This means that all external libs will need to implement these versus callbacks.
* Generators, and generator style functions are what allows us to use async/await.

###Generators

* easy way to build a generator: `const foo = promiseWrap(function* () => {})`
* the `function*` is the keyword that builds the generator

## Examples

* A setTimeout function could be written:
```
function sleep(time) {
  return new Promise((resolve) => setTimeout(resolve, time));
}
```

* Async/Await example:
```
export default async function getLikes () {
  const users = await getUsers();
  const filtered = await filterUsersWithFriends(users);
  return getUsersLikes(filtered);
}
```
