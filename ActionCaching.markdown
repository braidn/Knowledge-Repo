performed in the controller with just a couple of declarations

`caches_page :content`: Tells R3 to cache every request after the first  
`caches_action :content`: Tells R3 to execute filters but cache the content. `caches_page` doesn't ask for filters after first time