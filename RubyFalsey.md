* Only 'false` and `nil` are inherently false in Ruby
  * Unlike many languages, 0 is considered true in Ruby
  * Also the statement `'false'` is actually true in Ruby
* If you are looking for `nil` and there is any possibility of `false` turning up, then look for `nil` explicitly
    Because of this, ABSOLUTELY everything else in the language is considered true.