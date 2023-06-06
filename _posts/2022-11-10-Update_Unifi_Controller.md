---
title: Update Unifi Controller
date: 2022-11-10 07:00:00 -0500
categories: [unifi]
tags: [unifi]
---

## Update your controller

* SSH and login as root `sudo -i`

* User the one-liner baby!

```terminal
rm unifi-update.sh &> /dev/null; wget https://get.glennr.nl/unifi/update/unifi-update.sh && bash unifi-update.sh
```


### How to Install your Unifi Controller

[See the Easy Unifi Updater forum post](https://community.ubnt.com/t5/UniFi-Wireless/UniFi-Installation-Scripts-UniFi-Easy-Update-Scripts-Ubuntu-18/td-p/2375150)

* Copy the link location of the script (keep in mind version number will change!)

```terminal
https://get.glennr.nl/unifi/install/unifi-7.2.95.sh
```

* SSH into Controller VM & login as root

```terminal
sudo -i
```

* Make sure the ca-certificates package is installed

```terminal
apt-get update; apt-get install ca-certificates wget -y
```

* Download the script by executing the follwing command.  (Change it to your wanted version or see the "one liner" command)

```terminal
wget https://get.glennr.nl/unifi/install/unifi-7.2.95.sh
```

### ...or just install the latest and execute it all with a "one liner"

```terminal
rm unifi-latest.sh &> /dev/null; wget https://get.glennr.nl/unifi/install/install_latest/unifi-latest.sh && bash unifi-latest.sh
```

* Now run the script with the command below

```terminal
bash unifi-7.2.95.sh
```

Thx for being awesome Glennr!