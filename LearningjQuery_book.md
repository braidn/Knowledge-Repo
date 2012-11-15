###Notes

1. 99% of all jQuery methods return a jQuery object.
1. Many jQ or `$` objects are returned as an array of elements.
  1. This allows us to quickly get specific ones with the
     `.get(arrayIndex)` notation
  1. Another way is to simply use `[arrayIndex]` (note that there is no
     period used when using this shortcut)

###Diff of doc.ready and window.onload

1. `window.onload` is fired when __all__ documents have been
   successfully downloaded and the DOM is ready for manipulation
1. `(document).ready` is fired when the DOM is ready but, perhaps not
   all the documents have been downloaded.
