* `nuke` will only ever remove the `/opt/boxen` repository
  * when using this command it is best to pass `--force --all` to avoid failures
* To force an auto re-authorization:
  * remove the GITHUB API TOKEN from keychain. 

###Fun command line hacks

* Use `--restart-service serviceName` to restart a boxen controlled service
  * a good example of these are nginx, dnsmasq, psql 
