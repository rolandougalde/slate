# LAMP Stack installation

You may have heard something about the LAMP stack. That wouldn’t be surprising, since some of today’s most popular open source web applications — for example, WordPress, Joomla and Drupal — run on LAMP.

> Install Apache 2 Web server:

```shell
# Install apache2 web server
$ apt install apache2
```

> Install PHP 7.4 app server:

```shell
# Install php & wordpress required packages
$ apt install php php-common php-mysql php-gd php-imagemagic php-mbcrypt php-xml php-xsl php-zip php-gz
```

> Configure Aapache 2.

```shell
# Edit website configuration file
$ nano /etc/apache2/sites-availabe/site-com.conf

# Enable required "mods"
$ a2enmod ssl
$ a2enmod rewrite
$ a2enmod headers
```

We have sites written in HTML, we also have wordpress as CMS, the server should be provisioned as described:

*Chose a VM Host:* find a VM host with enough resources.

- Create the Virtual Machine
- Configure web server
- Configure website
- Clone website code
- Set file ssytem permisions
- Publish the website

`https://website.local`

<aside class="notice">
You must review all the <code>configurations</code> with your consultant.
</aside>

# Website deploy

## HTML Site deploy

- Create a source code directory
- Clone the website app code
- Set file system, directory and file permisions

> Create a source directory

```shell
# Create a directory
$ mkdir /var/www/website-local/
```

> Set file system, directory and file permisions

```shell
# Change owner and directory and file permisions
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
User      | test    | If set to true.
Password  | test    | If set to true.

<aside class="success">
Remember — check all the website menus links, images and pages.
</aside>

