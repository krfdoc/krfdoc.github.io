---
title: Git Commands
date: 2022-11-10 10:00:00 -0500
categories: [linux,plex]
tags: [linux,plex]
---

## Update Plex when hosted on a Linux server

* Download update .deb file from web GUI settings
* Use Filezilla or bitvise (some SFTP client) and copy file to home folder
* Enter:

```terminal
sudo dpkg -i <The_Newest_Plex_Version>.deb
```

Then reboot server

```terminal
sudo reboot now
```