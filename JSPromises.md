# JavaScript Promises

## Notes

* Async JS pattern that allows you to write less right leaning code.
* Always in a state of resolved or rejected.
* Control flow is used by chaining `then` and `catch` functions.

## Async/Await

* These patters derive from there implementation in C# and F#.
  * Looking up issues
* This feature relies heavily on _all_ functions returning a Promise.
  * This means that all external libs will need to implement these versus callbacks.

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