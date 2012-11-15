* `redirect_to :action => options` sends a temporary redirect to the specified options
* `redirect_to(path)` used to redirect the user to a specific URI
  * usually pass the location from app root: redirect_to("help/you_are_numb/morehelp")
* `redirect_to(:back)` pulls the user back to the URL in the [HTTP_REFERER][1] header
* When sending a redirect call, the new action doesn't have any intelligence of previous instance variables
  * This subverted with a facility called {{RailsFlash}}.
  * `, :notice => 'noticeInfo'` or `,:alert => "errorInfo"` can be used along with the redirect_to to make things more concise

[1]: https://en.wikipedia.org/wiki/HTTP_referrer