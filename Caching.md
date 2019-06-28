## Memcached

* Connecting to a running memcached server:
  ex: `telnet localhost 11211`

## Rails

Rails 3 offers three approaches to caching: (All R3 caching is URL based!!)

* [PageCaching][page]
* [ActionCaching][action]
* [FragmentCaching][frag]

caching is actually turned off by default in dev mode under config/environments. Turn on with: `config.action_controller.perform_caching = true`

ideas for [BadCache][bad] and choosing a [CachingStrategy][strategy]

[CacheSweepers][sweepers] are methods that can be called by a controller to remove existing caches

[page]: /PageCaching
[action]: /ActionCaching
[frag]: /FragmentCaching
[bad]: /BadCache
[strategy]: /CachingStrategy
[sweepers]: /sweepers