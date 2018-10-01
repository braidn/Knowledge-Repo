# PGP Keys

## Notes

## Setting Up A New Machine

* Import all keys from keybase
  * `curl https://keybase.io/<your-username>/key.asc | gpg --import`
* Import secret keys from keybase
  * Pull the secret key from keybase's web ui
  * `gpg --allow-secret-key-import --import keybase-private.key`
* Trust the keys.
  * `gpg --edit-key user@useremail.com`
  * `trust` at the gpg prompt
  * select the trust level and save

