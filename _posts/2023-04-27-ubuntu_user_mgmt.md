---
title: Ubuntu User Management
date: 2023-04-27 3:00:00 -0500
categories: [linux]
tags: [create-user,root]
---

[Ubuntu User Mgmt](https://ubuntu.com/server/docs/security-users)

## Create Super User in Linux & Use Root Shell

### Create New user

* if running as std user make sure to add sudo:

```terminal
adduser newuser
```

### Delete existing user

```terminal
deluser username
```

### Add a root (super) user
* As root user, run this command to add your new user to the sudo group
```terminal
gpasswd -a newuser sudo
```

### Change to root shell

* This will give you an interactive root shell at your current directory.  Type `exit` when done
```terminal
sudo -i
```

* This is effectively the same thing as `sudo -i`.   
```terminal
su
```

* Note that it will ask for the root password and not your login password.  These are not the same.  You may have to set or change the root password by running:
```terminal
sudo passwd root
```