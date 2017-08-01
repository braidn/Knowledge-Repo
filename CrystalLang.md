# Crystal Lang

## Notes

* Comes with a built in test/spec framework. Used by `crystal spec someFile.cr`
* Comes with a build in templating library called 'ecr'
  * much like erb for Ruby.

## Testing

* Crystal ships with a competent spec suite that is very familiar to RSpec.
  * I find this quite sad though since MiniTest under the hood is much more simple.
* Any file that ends in `_spec.cr` is considered a spec or test file.
* The overall design of the files are built using familiar `describe` and `it` blocks.
  * however if inclined, the `context` keyword is available.
* Requiring files and the spec helper starts at the very top of the file.
* Callback hooks (after and before) are available using: `Spec.before_each do; end` syntax
* All matchers are defined in the [Spec::Expectations][1] file

[1]: http://crystal-lang.org/api/Spec/Expectations.html
