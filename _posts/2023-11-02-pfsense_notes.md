---
title: pfSense Notes
date: 2023-11-02 3:00:00 -0500
categories: [pfsense]
tags: [pfsense]
---

## How to enable WAN interface management from shell

### disable packet filter

* Log into Shell (SSH or CLI via console)
* Disable packet filter entirely to access web interface from any interfaces.  Useful for temporary or first time setup only.  You will be vulnerable if left disabled!

```terminal
pfctl -d
```

* Enable it back:

```terminal
pfctl -e
```

## How to clear pfSense DHCP leases manually.  On YOUR terms!

In PfSense, instead of waiting for expired DHCP leases to be reclaimed, one may want to manually clear expired leases. 

From DHCP status you can go to ‘Show all configred leases‘ and click ‘Delete lease’ one by one, or you can use this method to clear them quicker.

### How To:

* Go to `Diagnostics` then Edit File
* Copy the following file path: `/var/dhcpd/var/db/dhcpd.leases`
* Click `Load`
* Now highlight and delete the blocks of leases you want to delete
* Click `save` when finished