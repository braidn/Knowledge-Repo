# Cockroach DB

## Notes

* It seems like UUID's are set by default for ID columns.
  * this is really handy but can trip up some ORM's.

## Elixir (Ecto)

* It's much easier to utilize the root user provided by Cockroach locally.
* When in Dev, Cockroach will be run with a user and no password.
