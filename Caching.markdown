Rails 3 offers three approaches to caching: (All R3 caching is URL based!!)

* {{PageCaching}}
* {{ActionCaching}}
* {{FragmentCaching}}

caching is actually turned off by default in dev mode under config/environments. Turn on with: `config.action_controller.perform_caching = true`

ideas for {{BadCache}} and choosing a {{CachingStrategy}}

{{CacheSweepers}} are methods that can be called by a controller to remove existing caches