---
title: Change Hostname
date: 2022-11-08 07:00:00 -0500
categories: [linux]
tags: [linux,hostname]
---

### How to Change your Hostname.  Cause ya

```bash
hostname NEW_NAME_HERE
```

This will only change the hostname until the next reboot.
To change permanently edit each of these files one by one:

```bash
sudo nano /etc/hostname
sudo nano /etc/hosts
```
Restart computer to apply changes
