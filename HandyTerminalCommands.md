# Handy Terminal Commands

* `echo 'flush_all' | nc localhost 11211` used to flush memcache server. This presupposed that your server is the local machine and listening on 11211
* MacOs' filesystem doesn't fire updates on symlinked file changes
  * To get around this, symlink the entire folder versus the file.
