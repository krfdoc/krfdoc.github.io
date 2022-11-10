---
title: Plex Notes
date: 2022-11-10 02:00:00 -0500
categories: [linux, plex]
tags: [linux,plex]
---

## Plex Notes

### Start/Stop Plex Media Server on Ubuntu

```bash
sudo systemctl start plexediaserver.service
```

### Metadata file path

```terminal
cd /var/lib/plexmediaserver/Library/'Application Support'/'Plex Media Server'
```

### CIFS/SMB Mounting (Section still needs work)

See fstab file examples.  Watch permissions, but haven't figured out completely yet. I've been using open/guest privledges  
Need to mount using "sudo mount -a" afer fstab cool. cool?

```bash
sudo mount -a
```