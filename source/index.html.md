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
  - openssl
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
$ adduser xanatos

# Add user to sudo group
$ usermod -G sudo xanatos
```

> Set up applications:

```shell
# With shell, you can just pass the correct header with each request
$ apt update
$ apt install net-tools unzip unrar aptitude nano 

# Configure Nano
$ nano /etc/nanorc
```

# LAMP Stack installation

> Install Apache 2 Web server:

```shell
$ apt install apache2
```

> Install PHP 7.4 app server:

```shell
$ apt install php php-common php-mysql php-gd php-imagemagic php-mbcrypt
```

> Configure Aapache 2.

```shell
$ nano /etc/apache2/sites-availabe/site-com.conf
$ a2enmod ssl
$ a2enmod rewrite
$ a2enmod headers
```

We have sites written in HTML, we also have wordpress as CMS, the server should be provisioned as described:

*Chose a VM Host:* find a VM host with enough resources.

Create the Virtual Machine

`Website finished`

<aside class="notice">
You must review all the <code>configurations</code> with your consultant.
</aside>

# Website deploy

## HTML Site deploy


```shell
chown -R root:root /var/www/* && find /var/www/ -type d -exec chmod 755 {} + && sudo find /var/www/ -type f -exec chmod 644 {} +
```

> Submit engine form:

```html
<!DOCTYPE html>
<html>
  <head>Website Name</head>
  <body>
    <form name="loginform" id="loginform" action="https://backend.website.local/default.aspx" method="post">
    <input type="text" name="Account" id="userbox" placeholder="Username">
   </form>
  </body>
</html>
```

This form submites credentials to the site backend.

### HTTP / HTTPS Request website

`http://example.com/`

### Website Parameters

Parameter | Default | Description
--------- | ------- | -----------
User      | test    | If set to true, the result will also include cats.
Password  | test    | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — check all the website menus.
</aside>

## WordPress Site deploy

```shell
chown -R www-data:root /var/www/* && find /var/www/ -type d -exec chmod 775 {} + && sudo find /var/www/ -type f -exec chmod 664 {} +
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> Configure Wordpress:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

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
