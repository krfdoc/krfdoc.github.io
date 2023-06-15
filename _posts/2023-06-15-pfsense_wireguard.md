---
title: pfSense Wireguard
date: 2023-06-15 8:00:00 -0500
categories: [pfsense]
tags: [wireguard,vpn]
---



[Tom's Video](https://www.youtube.com/watch?v=8jQ5UE_7xds)

[Tom's forum post](https://forums.lawrencesystems.com/t/getting-started-building-your-own-wireguard-vpn-server/7425)

## Tutorial: pfsense Wireguard For Remote Access

### Setting up on pfSense = Watch the first 11 minutes of the video

### Adding a single peer to pfSense

`start ~11:00 into the video`

### Linux Client-Side Setup

* Install wireguard
`apt-get install wireguard`

* Go to to the Wireguard config `cd /etc/wiregaurd` and then run the following command to generate the public and private keys for the server:

```terminal
umask 077; wg genkey | tee privatekey | wg pubkey > publickey
```

* Then run `cat privatekey` and copy it so we can put it in to the config file.
* or run `cat publickey` which is needed for setting up the peer in pfSense

* Create the local client's Wireguard config:
`nano /etc/wireguard/"urconfigname".conf`

* "urconfigname" is entered w/out quotes of course

```terminal
[Interface]
PrivateKey = <Your Private Key Goes Here>
Address=10.10.99.x/24
```
* please note the Address above (under interface), is for the client.  So for your network, it would be a 10.10.99.2 or .3 or .4 or .5 or whatever peer count you're up to

Run `wg-quick up "urconfigname"` to make sure the system comes up and run `wg-quick down "urconfigname"` to take down the interface.

On the linux client edit `/etc/wireguard/"urconfigname".conf` and now add the peer information:

```terminal
[Interface]
PrivateKey = <Your Private Key Goes Here>
 Address=10.10.99.x/24

[Peer]
# pfSense or other server machine
 PublicKey=<Public Key From server machine or pfSense>
 Endpoint=<Public IP>or<DynDNS>:51820
 # AllowedIPs = 0.0.0.0/0 # Forward all traffic to server
 AllowedIPs = 10.10.99.0/24, 10.10.1.0/24, 10.10.2.0/24, 10.10.3.0/27
```

* Don't forget to change to custom port listed in pfSense.  You're NOT using the default


### Additional Links/Videos

[How to build your own wireguard VPN server in the cloud - Tom's Vid](https://www.youtube.com/watch?v=7yC-gJtl9mQ)