# MariaDB Installation
*Basic configuration*

<aside class="notice">
This document was created as a part of academic simplest examples, it was never intended to use on a production server, our lab just covers <code>Ubuntu 22.04</code> and <code>MariaDB 10.6</code> setup.
</aside>

> MariabDB Secure Install

```shell
# Update package manager
$ apt update

# Install MariaDB
$ apt install mariadb-server-10.6

# Secure Installation
$ mysql_secure_installation

# Enter current password for root (enter for none): 
# OK, successfully used password, moving on...

# Change the root password? [Y/n] y
# ... Success!

# Remove anonymous users? [Y/n] y
# ... Success!

# Disallow root login remotely? [Y/n] y
# ... Success!

# Remove test database and access to it? [Y/n] y
# - Dropping test database...
# ... Success!
# - Removing privileges on test database...
# ... Success!

# Reload privilege tables now? [Y/n] y
# ... Success!

# All done!  If you've completed all of the above steps, your MariaDB
# installation should now be secure.

# Thanks for using MariaDB!
```
## Managing users

> Creating users:

```sql
CREATE USER 'sa'@'%' 
IDENTIFIED BY 'your_password';
```

> Grant user rights:

```sql
GRANT ALL PRIVILEGES ON *.* TO 'sa'@'%' 
IDENTIFIED BY 'your_password' 
WITH GRANT OPTION;
FLUSH PRIVILEGES;
```
## Create database & tables

> Create tables

```sql
CREATE DATABASE db_slater;

USE db_slater;

CREATE TABLE players  
( id INT NOT NULL AUTO_INCREMENT,  
  name VARCHAR(100) NOT NULL,  
  sports VARCHAR(50),
  PRIMARY KEY(id) );
```
