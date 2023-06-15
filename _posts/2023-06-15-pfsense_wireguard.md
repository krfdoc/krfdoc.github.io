---
title: pfSense Wireguard
date: 2023-06-15 8:00:00 -0500
categories: [pfsense]
tags: [wireguard,vpn]
---



[Tom's Video](https://www.youtube.com/watch?v=8jQ5UE_7xds)

[Tom's forum post](https://forums.lawrencesystems.com/t/getting-started-building-your-own-wireguard-vpn-server/7425)

## Tutorial: pfsense Wireguard For Remote Access

### Setting up = Watch the first 12 minutes of the video

### Adding a single peer to pfSense

`start ~11:00 into the video`

### Linux Client Side Setup

* Install wireguard
`apt-get install wireguard`

* Go to to the Wireguard config `cd /etc/wiregaurd` and then run the following command to generate the public and private keys for the server:

```terminal
umask 077; wg genkey | tee privatekey | wg pubkey > publickey
```

* Then run `cat privatekey` and copy it so we can put it in to the server config file.

* Create the /etc/wireguard/youtube.conf:
`nano /etc/wireguard/"urconfigname".conf`

* "urconfigname" is entered w/out quotes of course

```terminal
[Interface]
PrivateKey = <Your Private Key Goes Here>
Address=10.10.99.x/24
```
Run `wg-quick up "urconfigname"` to make sure the system comes up and run `wg-quick down "urconfigname"` to take down the interface.


### Additional Links/Videos

[How to build your own wireguard VPN server in the cloud - Tom's Vid](https://www.youtube.com/watch?v=7yC-gJtl9mQ)