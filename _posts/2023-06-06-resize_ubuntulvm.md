---
title: Resize Ubuntu default LVM space
date: 2023-06-06 9:00:00 -0500
categories: [linux]
tags: [ubuntu,lvm]
---

## Ubuntu: Extend your default LVM space

[Extend LVM Guide](https://packetpushers.net/ubuntu-extend-your-default-lvm-space/)



### Let's Begin


* Check root filesystem free space
```terminal
df -h
```

* To check for existing free space on your Volume Group (where it is left by the installer default settings), run the command `vgdisplay` and check for free space.  Look under the `Free PE / Size` row

* To use up that free space on your Volume Group (VG) for your root Logical Volume (LV), first run the `lvdisplay` command and check the Logical Volume size, then run `lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv` to extend the LV to the maximum size usable, then run `lvdisplay` one more time to make sure it changed.

* safasdfa
```terminal
safasf
    ```