---
title: Clear DHCP leases manually in pfSense
date: 2022-11-11 3:00:00 -0500
categories: [pfsense]
tags: [pfsense]
---

### How to clear pfSense DHCP leases manually.  On YOUR terms!

In PfSense, instead of waiting for expired DHCP leases to be reclaimed, one may want to manually clear expired leases. 

From DHCP status you can go to ‘Show all configred leases‘ and click ‘Delete lease’ one by one, or you can use this method to clear them quicker.

### How To:

* Go to `Diagnostics` then Edit File
* Copy the following file path: `/var/dhcpd/var/db/dhcpd.leases`
* Click `Load`
* Now highlight and delete the blocks of leases you want to delete
* Click `save` when finished