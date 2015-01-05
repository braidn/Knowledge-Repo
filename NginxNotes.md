## Notes

* Nginx can easily password protect portions of the website through http_basic_auth
  * Simply download the apache2-utils package and run `htpasswd -d /location username password`
  * Wire up the location of the file to the .conf file, with it being "Restricted"