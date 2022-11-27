# Database
## Postgresql
Server package _extra/postgresql_
psql command line _extra/postgresql-client_
Interface _community/pgadmin4_

### Setup
`sudo -u postgres psql` to login with superuser.

To login to postgres use `psql` command, this will log in with the user I'm currently using in linux (e.g. marco)

`CREATE DATABASE marco;` to allow login with marco user

`ALTER ROLE marco SUPERUSER;` to add superuser capabilities to marco user

### Usage
`\?` for help with psql commands, `\h` for sql commands
`\l` to list all databases (and users, groups and templates)
`\c webvalley` to connect to a database
`\d` to describe a database:
-   `\dt` tables
-   `\dv` views
-   `\ds` squences
-   `\du` to list roles

`\i file.sql` to import commands from an external file ([docs](https://www.postgresql.org/docs/current/tutorial-sql-intro.html))
`\s` for history
`\password user` to change a user's password

### Postgis
Postgis is an extension for spatial and geographic objects

Setup with `CREATE EXTENSION postgis;` to import basic geometry and geograpy ([](https://postgis.net/install/)[https://postgis.net/install/](https://postgis.net/install/))

## MongoDB
Interface _robo3t_

Command line _mongosh_ not installed in favor of _robo3t_
## Sqlite
`sqlite3 db.sqlite3`
*.tables* to list tables