---
title: Create SuperUser
date: 2023-04-27 3:00:00 -0500
categories: [linux]
tags: [create-user]
---

## Create SuperUser in Linux

### Create New user

```terminal
adduser newuser
```

### Add a root (super) user
* As root user, run this command to add your new user to the sudo group
```terminal
gpasswd -a newuser sudo
```