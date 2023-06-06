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

* At this point you have increased the size of the block volume where your root filesystem resides, but you still need to extend the filesystem on top of it. First, run `df -h` to verify your (almost full) root file system, then run `resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv` to extend your filesystem, and run `df -h` one more time to make sure you’re successful.

* And that’s it. You just allocated the free space left behind by the Ubuntu installer to your root filesystem. If this is still not enough space, continue on to the next section to allocate more space by extending an underlying disk.

### Use Space from Extended Physical (or Virtual) Disk

`More notes to come if/when I need them for this section`

* blah blah ...I actually did need to do this next section once.  It sucked.
```terminal
blah blah blah
    ```