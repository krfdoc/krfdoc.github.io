---
title: Debian Notes
date: 2023-10-26 9:00:00 -0500
categories: [linux]
tags: [debian]
---

## Change Hostname

* Modify nameservers here:
`/etc/resolv.conf`

* Not sure if this option persists!  More notes may be needed!

## Add Debian mirror/archvive/resource for apt

* Add the following in `/etc/apt/sources.list`

```terminal
deb http://deb.debian.org/debian/ bookworm main non-free-firmware contrib non-free
deb-src http://deb.debian.org/debian/ bookworm main non-free-firmware contrib non-free
```

## More notes someday

`More notes to come if/when I need them for this section`

* blah blah
```terminal
blah blah blah
    ```