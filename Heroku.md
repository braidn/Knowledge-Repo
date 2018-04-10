## Notes

* Good place to start if you need environment variables for an app
	* `heroku config --app {name}` should give them out

## CLI

* `heroku apps -A` to display all your apps. Lots of them hide for some reason.
* `heroku pg:backups restore $(heroku pg:backups public-url --app PRODUCTION) --app STAGING`
  * this backs up a staging app from a production apps snapshot.