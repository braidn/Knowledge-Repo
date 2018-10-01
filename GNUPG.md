# PGP Keys

## Notes

* Setting this up can be somewhat tricky on a new Mac

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
* Afterwards, a better prompt for this is Pinentry. Use the following to set it as the gpg agent:
  * create a new file: `touch ~/.gnupg/gpg-agent.conf` with the following

        pinentry-program /path/to/pinentry-mac
        default-cache-ttl 600
        max-cache-ttl 7200

* Restart the agent: `gpgconf --kill gpg-agent`
