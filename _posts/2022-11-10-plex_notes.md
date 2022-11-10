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

`cd /var/lib/plexmediaserver/Library/'Application Support'/'Plex Media Server'`

### CIFS/SMB Mounting (Section still needs work)

See fstab file examples.  Watch permissions, but haven't figured out completely yet. I've been using open/guest privledges  
Need to mount using "sudo mount -a" afer fstab cool. cool?

```bash
sudo mount -a
```

### fstab Examples

```terminal
# /etc/fstab: static file system information.
#
# Use 'blkid' to print the universally unique identifier for a
# device; this may be used with UUID= as a more robust way to name devices
# that works even if disks are added and removed. See fstab(5).
#
# <file system> <mount point>   <type>  <options>       <dump>  <pass>
# / was on /dev/ubuntu-vg/ubuntu-lv during curtin installation
/dev/disk/by-id/dm-uuid-LVM-AnFKoHrToGArXBS80lrQiAZh0RVLFTeXOrG5sXxp1jcEReq99oBErvHx1jQeNsGd / ext4 defaults 0 1
# /boot was on /dev/xvda2 during curtin installation
/dev/disk/by-uuid/d7ceb908-385f-415e-9e5d-315671e3add0 /boot ext4 defaults 0 1
/swap.img	none	swap	sw	0	0
//10.10.1.6/Music /media/music cifs guest,uid=1000,iocharset=utf8 0 0
//10.10.1.6/Video /media/video cifs guest,uid=1000,iocharset=utf8 0 0
//10.10.1.6/Scratch /media/scratch cifs guest,uid=1000,iocharset=utf8 0 0
```

```terminal
UUID=19c001b1-4663-48a6-b2ba-1f41a157c767 / ext4 defaults 0 0
/swap.img	none	swap	sw	0	0
//10.10.1.6/Music /media/music cifs guest,uid=1000,iocharset=utf8 0 0
//10.10.1.6/Video /media/video cifs guest,uid=1000,iocharset=utf8 0 0
```