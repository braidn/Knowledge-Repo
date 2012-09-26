###Get Running Quik $ Dirty

* `bundle install --deployment` if first time AND or updated Gemfile
* `RAILS_ENV=production rake db:migrate` if new migrations are needed or
  first deploy
* `RAILS_ENV=production rake assets:precompile` staic those assets.
  Requires rubyracer gem or node to be installed on the machine.
