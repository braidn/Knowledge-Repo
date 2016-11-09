#Vue Framework

##Notes

* Components, kind like Angular 1.5 and Angular 2.0 are core tenants of a Vue app.
* Directives are also borrowed heavily from Angular
  * some of the build in ones are used a lot: `v-if, v-on, v-cloak`
* [Some comparisons with other frameworks][1]

##Veux

* State management layer that's like a Flux Dispatcher made love to Elm.
* Don't get hung up in splitting everything into separate files.
  * Until you need it, a complete store could be written in a single file (store.js for example).

[1]: https://rc.vuejs.org/guide/comparison.html