Two types of cookies: sessions and persistent

###Session Cookies

Get destroyed one the user closes the browser

###Persistent Cookies

Expire at a predetermined time set within the cookie itself

###Managing Cookies

* Setting a cookie is as easy as calling response.set_cookie and giving it a name and value as parameters
  * `response.set_cookie "foo", "bar"
  * 'foo' is the key and 'bar' is the param
* To delete a cookie just call `response.delete_cookie "cookieKey"`