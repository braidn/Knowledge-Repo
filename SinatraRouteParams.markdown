* basisc : `get '/one/:param1'`
* all params get shoved into the params array on load
  * they are all retrievable by calling '#{params[:paramName]}'
* For PUT and POST you are __not required__ to put the params in the url request if you don't want to
* Wildcards can be formed by: `get '/one*'`
  * these get thrown into a very unique array called: `params[:splat]`
    * unlike the other params, this is another array that you can sift through (makes sense really since it consumes all of the parameters passed to it)
* In sinatra, the first sufficient match will __always__ win, hands down.
  * watch it while using splats in this case.
* Regexp is allowed by using: `get %r{\w[^aeiou](Bla|Bla)} do`
* To halt a specific request: pass `halt 5000` at the end of the block body
* Routes can have a redirect method: redirect 'ur', optionalRedirectCode (301 or 302)
  * if no redirect is chosen than things default to 302 (temp redirection)
* If items are placed in a folder called 'public', the folder will be witheld from the uri
  * `/public/public.html` will result in a uri that reads: localhost:port/public.html
  * This is the only folder in the root dir that has this functionality.