#Cloud 66

###Docker

* Env variables are not exposed to the docker instance early on so in a docker 
file, to say migrate a database, the migrations need to be defered using `ONBUILD`:
  * ex: `ONBUILD RUN MIX_ENV=prod mix ecto.migrate`

###Databases

* The username of the database is the name of the database.
  * so something staging would be user something_staging

###Deploy Hooks

* When installing node based dependencies install them during the `after_checkout` hook.
 * [Example][1]

[1]: https://gist.github.com/braidn/1c583c77ba1eec8782bc