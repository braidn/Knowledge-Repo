# Postgres Ltree Extension

## Notes

* The nlevel and subpath functions below are handy for writing efficient updates to a tree:
  * ex: `update tree set path = subpath(path, nlevel('A.C')-1) where path <@ 'A.C';`
* The concatenation operator below is great for moving branches around a tree:
  * ex: `update tree set path = 'A.B.G' || subpath(path, 1) where path <@ 'A.C';`

## Functions

* `nlevel`: returns a given number of levels in a path.
* `subpath`: takes a path and number and returns the subpath below it.
* `||:` used to concatenate a path together
  * ex: `select 'A.B.G' || subpath(path, 1) as concatenated from tree where path <@ 'A.C';`
