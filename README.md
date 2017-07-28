# Useful Commands

## Linux 

- Alter version default of Python install in on Ubuntu
    * `$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 10`

## PostgreSQL
- Create user with password
    * `postgres=# CREATE USER linus WITH PASSWORD 'linux';`

- Create DATABASE
    * `postgres=# CREATE DATABASE example_db;`

- List all databases
    * `postgres=# \l`

- List all databases with details
    * `postgres=# \l+`

- List users accounts
    * `postgres=# \du`

- Add Privileges
    * `postgres=# GRANT ALL PRIVILEGES ON DATABASE example_db to linus;`
