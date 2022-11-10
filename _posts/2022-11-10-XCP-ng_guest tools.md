---
title: XCP-ng Guest Tools
date: 2022-11-10 4:00:00 -0500
categories: [xcp-ng]
tags: [xcp-ng]
---

## How to install XCP-ng guest tools on a Windows VM (easiest method)

* Acquire `citrix-vm-tools-9.3.0` from Citrix website (add link someday.  For now it's in your share folder)
* While VM is stopped, toggle `Windows Update Tools` from `Advanced` tab on XCP-ng
* Start VM.  Check for updates.  Restart required
* Next, check for updates but select `Install optional updates`.  You'll find it somewhere in the Windows Update settings under "advanced" I believe
* Another restart will be required
* Load the `citrix-vm-tools-9.3.0` files on the VM itself.  Wizard will bring ya home (plus another restart probably required)

[Tom's Video](https://www.youtube.com/watch?v=AAHZX7MdEG0)

## Ubuntu Instructions

```bash
apt install xe-guest-utilities
```

### Alternate - Manual Install

* Attach the guest tools ISO
* Then inside the VM as root:

```bash
mount /dev/cdrom /mnt
bash /mnt/Linux/install.sh
umount /dev/cdrom
```
No need to reboot even tho I normally do anyways.

* Make sure to eject the guest tools ISO when done

## Video Res Issues.  Start here

[XCP-ng VM's display res locked](https://forums.lawrencesystems.com/t/xcp-ng-vms-display-resolution-locked/10988)

