###For Rails =>
provides a dead simple method to generate them: `rails g test_unit:integration {{NameOfTest}} `

* When your previous response was a redirect you can call `follow_redirect!` to jump to the controller that was redirected to.
  * This would allow you to continue using the `assert template 'action'` without having to define the new controller.
  * A very basic clear of sorts when dealing with these types of tests.
* Ripe for story based scenario tests using DSLs
  * If you do this, make sure to use `open_session do |user|` to create an open session that you can assign defined methods to (logs_in, logs_out, etc)