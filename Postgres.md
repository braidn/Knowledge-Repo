# Postgres

## Notes

* Sometimes new databases don't have access to UUID functions (v10.1)
  * this can be remedied by connecting to the database and: `CREATE EXTENSION IF NOT EXISTS "uuid-ossp";`
