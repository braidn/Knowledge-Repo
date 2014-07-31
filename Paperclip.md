* All of the below are for paperclip, a handy gem for dealing with uploaded images
  * [Repo][1] (from the guys/gals behind thoughtbot)
* Certain tasks require you to pass a "Class to them".
  * This is done by `rake 'paperclip:taskname' CLASS=className`
  * Sort of a weird PIA vs using [className] rake syntax
* If for any chance you need to import images into Paperclip:
  * build their url using `File.join(path, path, etc)`
  * stuff this url into `URI.parse(url)` and pass the result to the attachment attr.

###Spree

* When definining the CLASS var use the Spree namespace
  * `Spree::Image`

[1]: https://github.com/thoughtbot/paperclip
