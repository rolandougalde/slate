# Cron Jobs

## Set up SSH Keys on a Linux System

- Create the ssh key pair using `ssh-keygen` command.
- Copy and install the public ssh key using `ssh-copy-id` command on a Linux server.
- Add the working user to sudo or wheel group admin account.
- Disable the password login for root account.
- Test your password less ssh keys login using `ssh user@server-name` command.

**RSA Keys:**
```
$HOME/.ssh/id_rsa– contains your private key.
$HOME/.ssh/id_rsa.pub – contain your public key.
```

**Backup Script**

```shell
# Create websites backup starting at at 1:00 a.m.
0 1 * * * /bin/tar -zcf /home/davidx/backups/app-code-$(date +\%Y_\%m_\%d_\%H_\%M).tar.gz /var/www
```

**Sync script**

```shell
 # Sync websites content every 10 minutes
*/10 * * * * /usr/bin/rsync -az --delete /var/www/ user@server02:/var/www/ && /usr/bin/rsync -az --delete /var/www/ user@server03:/var/www/
```

**Permisions script**

```shell
# Reset web folder permisions at 3 a.m.
# Wordpress or Joomla permisions schema
* 3 * * * /usr/bin/find /var/www/ -type d -exec chmod 775 {} + && sudo find /var/www/ -type f -exec chmod 664 {} +
#
# Reset web folder permisions at 3 a.m.
# HTML or Jamstack permisions schema
* 3 * * * /usr/bin/find /var/www/ -type d -exec chmod 755 {} + && sudo find /var/www/ -type f -exec chmod 644 {} +
```
