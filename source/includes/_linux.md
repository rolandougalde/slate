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
