# Cron Jobs

## Set up SSH Keys on a Linux System
- Create the ssh key pair using `ssh-keygen` command.
- Copy and install the public ssh key using `ssh-copy-id` command on a Linux server.
- Add the working user to sudo or wheel group admin account.
- Disable the password login for root account.
- Test your password less ssh keys login using `ssh user@server-name` command.

## Generating keys on the source server 

> Generates a private and public keys:

```shell
ssh-keygen
```

> Output:

```text
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/vivek/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/vivek/.ssh/id_rsa.
Your public key has been saved in /Users/vivek/.ssh/id_rsa.pub.
The key fingerprint is:
80:5f:25:7c:f4:90:aa:e1:f4:a0:01:43:4e:e8:bc:f5 vivek@desktop01
The key's randomart image is:
+--[ RSA 2048]----+
| oo    ...+.     |
|.oo  .  .ooo     |
|o .o. . .o  .    |
| o ...+o.        |
|  o .=.=S        |
| .  .Eo .        |
|                 |
|                 |
|                 |
+-----------------+
```

## Copying keys

Copying keys to destination servers:

```shell
ssh-copy-id user@server02
```

## RSA Keys

> Private and public keys:

```text
$HOME/.ssh/id_rsa– contains your private key.
$HOME/.ssh/id_rsa.pub – contain your public key.
```

## Backup Scripts

> Creates apps code backup starting at at 1:00 a.m.

```shell
0 1 * * * /bin/tar -zcf /home/davidx/backups/app-code-$(date +\%Y_\%m_\%d_\%H_\%M).tar.gz /var/www
```

> Creates a MongoDB server backup, then compress the info in a TGZ file:

```shell
0 4 * * * mongodump --out=/home/servicedesk/backups/rocket-chat && tar -zcvf /home/servicedesk/backups/rocket-chat-$(date +\%Y-\%m-\%d-\%H-\%M).tar.gz /home/servicedesk/rocket-chat/
```

> Sync websites content every 10 minutes

```shell
 */10 * * * * /usr/bin/rsync -az --delete /var/www/ user@server02:/var/www/ && /usr/bin/rsync -az --delete /var/www/ user@server03:/var/www/
```

## Permisions script

> Permisions and ownership scripts:

```shell
# Reset web folder permisions at 3 a.m.
# Web apps permisions schema
* 3 * * * /usr/bin/find /var/www/ -type d -exec chmod 775 {} + && sudo find /var/www/ -type f -exec chmod 664 {} +
#
# Reset web folder permisions at 3 a.m.
# HTML or Jamstack permisions schema
* 3 * * * /usr/bin/find /var/www/ -type d -exec chmod 755 {} + && sudo find /var/www/ -type f -exec chmod 644 {} +
```
