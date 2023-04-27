---
title: Install deb Package
date: 2023-04-25 5:00:00 -0500
categories: [linux]
tags: [(dot)deb]
---

## How to Install a .deb package

### Method 1

* Run:
```terminal
sudo dpkg -i DEB_PACKAGE
```
If `dpkg` reports an error due to dependency problems, you can run `sudo apt-get install -f` to download the missing dependencies and configure everything

* To remove:
```terminal
sudo dpkg -r PACKAGE_NAME
```

### Manual deb install

```terminal
sudo apt-get install ./package.deb
```
or

* Include `-f` to install dependacies
```terminal
sudo apt-get install -f ./package.deb
```