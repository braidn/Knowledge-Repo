##Notes

* To exclude a link add `data-no-turbolinks: true` to any link_to or button helper
* Animations are totally doable although are not on by default
	* [this SO article][1] goes fairly deeply down this rabbit whole

###Gotchas

* Lots of folks shore up stuff in document.ready, which won't work using TL
	* to get around this, instead bind to the page:change event

###Non Rails4

* add the gem to your gemfile and bundle/install
* add the `//= require turbolinks` to your application.js.coffee manifest

###Alternatives

* [WiseLinks][2]

[1]: http://stackoverflow.com/questions/11679567/using-css-for-fade-in-effect-on-page-load/11681331#11681331
[2]: https://github.com/igor-alexandrov/wiselinks
