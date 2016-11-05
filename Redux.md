# Redux

## Notes

* All state data is housed in a state object. 
  * This object mainly resembles one large JS object and is read only.
* All actions produce an object (JS) that define the intent to modify the object.
  * A seemingly large switch statement hinges on the types of a actions, and makes responses accordingly.
* Actions pass information to a Reducer which is where the state will change.
  * Basically these calculate the next state of the application.
* Not all state needs a store. Some can perfectly survive in local component state.
  * especially if the state is only used by the one component and does not mutate heavily.

## 'Best' Practices

* The flatter the data, the better.
  * A way to do this semi-automagically is to use [Normalizer][1].
  * Returning data like this is always going to be wildly easier for all JS apps.
* Make actions super simple, and slim.
  * Extract actions that create data, use XHR requests, or induce side effects into action creators.
* Utilize reducer composition to break up the almost inevitably large 'root reducer'.
  * These specialized reducers will break up the large main reducer and make things easier to test.

## Testing

* When testing action creators, test that the correct action is being generated.
* When testing reducers, test that the next state is expected from the data passed in.

[1]: https://github.com/paularmstrong/normalizr