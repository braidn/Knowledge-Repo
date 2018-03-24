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

* The __flatter the data, the better__.
  * A way to do this semi-automagically is to use [Normalizer][1].
  * Returning data like this is always going to be wildly easier for all JS apps.
  * This should almost be a default if an API returns deeply nested items (think JSONAPI).
* Make actions super simple, and slim.
  * Extract actions that create data, use XHR requests, or induce side effects into action creators.
* Utilize reducer composition to break up the almost inevitably large 'root reducer'.
  * These specialized reducers will break up the large main reducer and make things easier to test.
* Search for immutability, it will calm down on the overall component updates which is an easier win.

## Store

* A collection of reducers that has three primary methods:
  1. `getState`: get the initial state of the store or the current state.
  1. `dispatch(:action)`: dispatch an action to the store. A reducer will grab the action.type and payload and update the store accordingly.
  1. `subscribe`: Subscribe to the changing state of the store.
* Absolutely any state change should occur due to a dispatch call.

## Reducer

* Pure function that takes the state of your application, an action and returns the next state
* Really just gigantic switch statements.
* Often times returns the state/current state if no action type matches the reducer
* These really require no external library (Redux) and are just simple, pure functions.

## Reducer Compositon

* Tenant of JS/Redux where you compose reducers together.
* This is usually done when dealing with array's of objects.
  * One reducer is implemented to iterate over the collection and passes actions/state (single item) into another reducer.
  * This does leave one single reducer at the top of the state tree. This would be the dispatcher in Flux.
* This is pretty common in Redux style apps so there exists a `combineReducers` function from the Redux lib.
  * This function just takes an object with keys of the state tree and values being the reducers for each state field.

## Testing

* When testing action creators, test that the correct action is being generated.
* When testing reducers, test that the next state is expected from the data passed in.
  * this can be done easily by setting expected before and after state objects and invoking the reducer with the action
* A handy way to make sure reducers don't mutate state is to use a [library like deep-freeze][2] when testing

## File System

* Since there is really no 'convention' around how reducers/actions are stored, 
file systems can be deeply nested and messy.
* This causes developers to hop from file to file and sometimes get lost.
* There is a pattern called [Ducks][duk] that alleviates this constant context switching.
  * Each module exports a default function called `reducers()`,
  * exports its action creators as functions,
  * exports it's action types in the form of: `module-app-name/reducer/ACTION_TYPE`

[1]: https://github.com/paularmstrong/normalizr
[2]: https://github.com/substack/deep-freeze
[duk]: https://github.com/erikras/ducks-modular-redux
