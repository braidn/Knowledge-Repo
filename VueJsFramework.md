#Vue Framework

##Notes

* Components, kind like Angular 1.5 and Angular 2.0 are core tenants of a Vue app.
* Directives are also borrowed heavily from Angular
  * some of the build in ones are used a lot: `v-if, v-on, v-cloak`
* [Some comparisons with other frameworks][1]
* Could use a simple structure of components, stores (state), services (updates state).
* _Props_: are local vars that contain data passed from the parent elements.
  * Generally when passing props, they are passed like `:propName="propVal"`
  * These are defined in the templates and then passed to all child components declared in script.
  * It's _best_ to pass only required methods from the store to children, never the whole store.
* Special events are handled on elements using the `@keyup='someMethod'` syntax.
* Data methods can be used to set up initial v-model values.

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

##Gotchas

* When running the Vue Webpack loader, the `template`, `style`, and `script` tags in .vue files 
are required for the component to properly resolve.
* All prop values are passed as strings. This is somewhat trippy to me.

[1]: https://rc.vuejs.org/guide/comparison.html