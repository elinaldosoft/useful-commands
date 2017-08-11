# Useful Commands

## Linux 

- Alter version default of Python install in on Ubuntu
    * `$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 10`
- RealPath of File (Absolute Path)
    ``` 
    $ realpath mysqld.cnf
    /etc/mysql/mysql.conf.d/mysqld.cnf 
    ```
- Enable NoPassword for privileges of sudo
    * `sudo visudo`
    * `user ALL=(ALL:ALL) NOPASSWD:ALL`
### NFS
    - Install On the Client 
        * `sudo apt-get install nfs-common`
    - Error `OSError: [Errno 37] No locks available`
        * `sudo systemctl enable rpc-statd  # Enable statd on boot`
        * `sudo systemctl start rpc-statd  # Start statd for the current session`

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

## Mysql
- Dump remote database `p` it is necessary when it does it requires a password  
    * `mysqldump -r output.sql -u user -p -d database -h localhost`
- Install MysqlServer
    * `apt-get install mysql-server`
- Add file for it's not asking password & user
    * touch ~/.my.cnf
    ```
    [client]
    user=mysqluser
    password=mysqlpass
    ```
- Allow access remote MysqlServer
    * vi /etc/mysql/mysql.conf.d/mysqld.cnf
    * alter from `bind-address = 127.0.0.1` to `bind-address = 0.0.0.0`
    * `sudo /etc/init.d/mysql restart`
- Create user with access remote
    * `mysql> CREATE USER 'jonhslow'@'%' IDENTIFIED BY 'winterfell' `
- Create Database
    * `mysql> CREATE DATABASE name_database; `
- Add Privileges for access database
    * `mysql> USE name_database;`
    * `mysql> GRANT ALL PRIVILEGES ON name_database TO 'jonhslow'@'%';`
- Restore Database
    * `mysql -u <user> -p <password> <name_database> < database.sql`