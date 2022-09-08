---
title: Linux Server Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - html
  - css
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Linux Server Documentation Reference
---

# Linux CLI Reference

Hello, this site was built thinking about needs of IT Infrastructure proffesionals who needs a day by day tool, that helps to get the job done insted of start looking on for poor customized solutions.

The code is an important part of DevOps team nowadays, you can pick commands to use directly on the console or to build custom automation scripts.

This site is and example API documentation page was created with [Slate](https://github.com/rolandougalde/slate).

# Linux Installation

Ubuntu Linux Server LTS, installation steps & file definition. Configure network, create users.

> Post install configuration tasks:
```shell
# With shell, you can just pass the correct header with each request
apt update
apt dist-upgrade

# Network configuration, YAML

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

# LAMP Stack installation

> Install `Apache 2` Web server:
```shell
apt install apache2
```
> Install `PHP 7.4` app server:
```shell
apt install php php-common php-mysql
```
> Configure `Aapache 2`.
```shell
nano /etc/apache2/sites-availabe/site-com.conf
```


Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Website finished`

<aside class="notice">
You must review all the <code>configurations</code> with your consultant.
</aside>

# UX File system permissions

## Close site folder


```shell
chown -R root:root /var/www/* && find /var/www/ -type d -exec chmod 755 {} + && sudo find /var/www/ -type f -exec chmod 644 {} +
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Open file permisions

```shell
chown -R www-data:root /var/www/* && find /var/www/ -type d -exec chmod 775 {} + && sudo find /var/www/ -type f -exec chmod 664 {} +
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

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

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

