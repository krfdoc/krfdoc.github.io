---
title: Update Plex on Linux
date: 2022-11-10 10:00:00 -0500
categories: [plex]
tags: [linux,plex]
---

## Update Plex when hosted on a Linux server

* Download update .deb file from web GUI settings
* Use Filezilla or bitvise (some SFTP client) and copy file to home folder
* Enter:

```bash
sudo dpkg -i <The_Newest_Plex_Version>.deb
```

Then reboot server

```bash
sudo reboot now
```