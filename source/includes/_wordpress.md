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
