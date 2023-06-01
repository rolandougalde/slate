---
title: Linux Server CLI Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - html
  - css
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - mariadb
  - openssl
  - cron
  - docker
  - errors
  
search: true

code_clipboard: true

meta:
  - name: description
    content: Linux Server Documentation Reference
---

# Linux CLI Reference

Hello, this site was built thinking about needs of IT Infrastructure proffesionals who needs a day by day tool, that helps to get the job done insted of start looking for poor customized solutions.

The code is an important part of DevOps team nowadays, you can pick commands to use directly on the console or to build custom automation scripts.

This site is and example API documentation page was created with [Slate](https://github.com/slatedocs/slate).

# Linux Installation

Ubuntu Linux Server LTS, installation steps & file system definition.

- Network Configuration
- Server Update
- Install tools
- Create users and groups
- Set up applications

> Network configuration:

```yaml
# Note, this config was written is YAML, tabs should be respected*
# This is the network config written by 'subiquity'
network:
   ethernets:
     ens160:
       addresses:
       - 192.168.101.29/22
       gateway4: 192.168.100.1
       nameservers:
         addresses:
         - 192.168.100.7
         - 192.168.100.9
         search:
         - domain.com
   version: 2
```

> Server update:

```shell
# With shell, update the server
$ apt update
$ apt dist-upgrade

# SNAP update
$ sanp refresh
```
> Create user and groups:

```shell
# Create the SFTP user
$ adduser davix

# Add user to sudo group
$ usermod -G sudo davix
```

> Set up applications:

```shell
# Install common used packages
$ apt update
$ apt install nano net-tools unzip unrar aptitude smnpd

# Configure Nano
$ nano /etc/nanorc
```

## WordPress Site deploy

```shell
chown -R www-data:root /var/www/* && find /var/www/ -type d -exec chmod 775 {} + && sudo find /var/www/ -type f -exec chmod 664 {} +
```
> Wordpress configuration file:

```php
/** Wordpress configuration file */

// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define('DB_NAME', 'db-blog-domian-local');

/** MySQL database username */
define('DB_USER', 'wp-user');

/** MySQL database password */
define('DB_PASSWORD', 'password');

/** MySQL hostname */
define('DB_HOST', 'website-db');

/** Database Charset to use in creating database tables. */
define('DB_CHARSET', 'utf8mb4');

/** The Database Collate type. Don't change this if in doubt. */
define('DB_COLLATE', '');

/** Memory limit */
define('WP_MEMORY_LIMIT', '128M');
```

This file should be tested.

<aside class="warning">Avoid special characters typed in a line, user <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Remove website

```shell
-rm -r /var/www/site
```

> Remove website config file

```shell
a2dissite site-com.conf
-rm -r /etc/apache2/sites-available/site-com.conf
```

This command deletes a specific site config file.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete
