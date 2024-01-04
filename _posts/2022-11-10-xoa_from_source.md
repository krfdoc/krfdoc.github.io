---
title: Build Xen Orchestra from Source
date: 2022-11-10 3:00:00 -0500
categories: [xcp-ng]
tags: [xcp-ng,xoa]
---

## Here is the new Tom Lawrence guide.  Update as necessary

* I guess this page may need a little work

[NEW Tom Lawrence Video](https://youtu.be/fuS7tSOxcSo?feature=shared)

## How to update your Xen Orchestra Instance

[Xen Orchestra Installer/Updater - Github ronivay](https://github.com/ronivay/XenOrchestraInstallerUpdater)

* Keith, please add command to update git branch so you can run the updated script from ronivay and then choose update.  That should be all that's needed really to update.

## How to build Xen Orchestra from source

* Don't forget to update your VM and all that jazz.  Use Debian or Ubuntu of course.  Then, install git

```terminal
sudo apt install git
```

* Clone the repository

```terminal
git clone https://github.com/ronivay/XenOrchestraInstallerUpdater.git
```

* Copy the sample config to the real config.  No real changes needed from default unless you go the port 443 route w/ certs.  That's always fun right?

```terminal
cp sample.xo-install.cfg xo-install.cfg
```

* cd into your home dir and run `sudo ./xo-install.sh`  that's it

* Login to VM using IP/Hostname of VM running the install.  Default credentials:

```terminal
user: admin@admin.net
pass: admin
```

### Links and Video

[Tom's blog post](https://forums.lawrencesystems.com/t/how-to-build-xo-from-sources-on-debian-10-using-xenorchestrainstallerupdater/4597)

Lawerence Systems: How to build XO from sources on Debian 10 (or Ubuntu) using XenOrchestraInstallerUpdater

[![See Tom build!](https://i.ytimg.com/vi/bq1iKO-0jWs/hqdefault.jpg?)](https://www.youtube.com/watch?v=bq1iKO-0jWs&t=10s "See Tom build!")

## XCP-ng Links

[Official Guide - Networking](https://xcp-ng.org/docs/networking.html#manage-physical-nics)