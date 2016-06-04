# L2 Linux Security

## Package Source Lists
### `/etc/apt/sources.list`
All of your available package sources are listed in this file

## Updating Available Package Lists
### sudo apt-get update
One of the most important and simplest ways to ensure your system is secure is to keep your software up to date with new releases. 

## Upgrading Installed Packages
### sudo apt-get upgrade

## Other Package Related Tasks
### `man apt-get`
Check out everything you can do
### `sudo apt-get autoremove`
automatically remove some packages 
### `sudo apt-get install (finger)`

## Discovering Packages
### packages.ubuntu.com

## Using Finger
This application will look up various pieces of information about a user, and display it to an easy-to-read format.
### `finger`
Output all of the users currently logged in to the system.
### `finger user_name`
See additional information about a specific user.

## Introduction to /etc/passwd
Stores information about each user.
### `vagrant:x:1000:1000::/home/vagrant:/bin/bash`
* vagrant: user name
* x: used to store encrypted password, now just insert a character
* 1000: user ID
* 1000: group ID
* :" ": to store a better description about the user
* /home/vagrant: default home directory
* /bin/bash: default shell

## Creating a New User
### `sudo adduser user_name`

## Connecting as the New User
### `ssh user_name@127.0.0.1 -p 2222`
* ssh: the application we use to remotely connect to the server.
* 127.0.0.1: the IP address we want to connect to.
* student@: the user we want to log in as.
* -p 2222: connect using port 2222.

## Introduction to etc sudoers
### `/etc/sudoers`
The list of users that are allowed to do "sudo" commands
### `includedir /etc/sudoers.d`
Look through any files in /etc/sudoers.d and include those as if they were written within this file
### `sudo ls /etc/sudoers.d`
Check out who can use "sudo"!

## Giving Sudo Access
### `sudo cp /etc/sudoers.d/vagrant /etc/sudoers.d/user_name`
### `sudo nano /etc/sudoers.d/user_name`
* **user_name** ALL(=ALL) NOPASSWD:ALL
* <https://help.ubuntu.com/community/Sudoers>

## Resetting Passwords
### `sudo passwd -e student`

## Generating Key Pairs
### `ssh-keygen`
Will generate a pub and a private key.

## Supported Key Pairs
The possible values are `rsa1` for protocol version 1 and `dsa`, `ecdsa`, `ed25519`, or `rsa` for protocol version 2.

## Installing a Public Key
### `mkdir .ssh`
Make this directory in home directory.
### `touch .ssh/authorized_keys`
### `chmod 700 .ssh`
### `chmod 644 .ssh/authorized_keys`
Set the permissions.
### `ssh user_name@127.0.0.1 -p 2222 -i ~/.ssh/your_key_pair_file_name`

## Forcing Key Based Authentication
### `sudo nano /etc/ssh/sshd_config`
**PasswordAuthentication no**
### `sudo service ssh restart`

## Introduction to File Permissions
### `ls -al`
**d rwx r-x r-x** file or directory / owner / group / everyone

## Octal Permissions
r = 4, w = 2, x = 1

## chgrp and chown
### `chown` owner_name file_name
change the owner on the file.
### `chgrp` group_name file_name

## Default Ports for Popular Services
### 80   - HTTP
### 443  - HTTPS
### 22   - SSH
### 21   - FTP
### 110  - POP3
### SMTP - 25

## Intro to UFW
### `sudo ufw status`
Verify if the Ubuntu built-in firewall is active.
### `sudo ufw default deny incoming`
Deny all incoming requests.
### `sudo ufw default allow outgoing`
Allow all outgoing requests.

## Configuring Ports In UFW
### `sudo ufw allow ssh`
Support SSH.
### `sudo ufw allow 2222/tcp`
Allow all TCP connections through Port 2222. (Vagrant set up SSH on Port 2222)
### `sudo ufw allow www`
Allow HTTP 
### `sudo ufw enable`
Enable the firewall

