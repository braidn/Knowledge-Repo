## Notes

* All of the below are for paperclip, a handy gem for dealing with uploaded images
  * [Repo][1] (from the guys/gals behind thoughtbot)
* Certain tasks require you to pass a "Class to them".
  * This is done by `rake 'paperclip:taskname' CLASS=className`
  * Sort of a weird PIA vs using [className] rake syntax

###Spree

* When definining the CLASS var use the Spree namespace
  * `Spree::Image`

[1]: https://github.com/thoughtbot/paperclip
