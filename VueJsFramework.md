#Vue Framework

##Notes

* Components, kind like Angular 1.5 and Angular 2.0 are core tenants of a Vue app.
* Directives are also borrowed heavily from Angular
  * some of the build in ones are used a lot: `v-if, v-on, v-cloak`
* [Some comparisons with other frameworks][1]

##Veux

* State management layer that's like a Flux Dispatcher made love to Elm.
* Comprised of 4 objects:
  * _State_: Beginning state for the application.
  * _Mutations_: functions that mutate the state object. They receive the state as a first parameter
followed by additional parameters. Must be synchronous.
  * _Actions_: Async functions that can cause side effects.
  * _Getters_: Similar to actions but without the side effects and usually return state info.
* Don't get hung up in splitting everything into separate files.
  * This one file is often called: `store.js`
  * Until you need it, a complete store could be written in a single file (store.js for example).

[1]: https://rc.vuejs.org/guide/comparison.html