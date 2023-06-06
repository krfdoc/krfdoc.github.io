---
title: Uptime Kuma
date: 2023-06-01 8:00:00 -0500
categories: [docker]
tags: [uptimekuma]
---

## Kuma Links PENDING NOT UPDATE YET AS YOU CAN SEE

[UpTime Kuma - Github](https://github.com/louislam/uptime-kuma)

### Docker Compose

```terminal
---
version: "3.1"

services:
  uptime-kuma:
    image: louislam/uptime-kuma:1
    container_name: uptime-kuma
    volumes:
      - /home/krf/docker_volumes/uptime-kuma/data:/app/data
    ports:
      - 3001:3001
    restart: unless-stopped
    security_opt:
      - no-new-privileges:true
```

### Update Kuma

* Just follow same produre as portainer update.  Don't have to use CLI tho.  
* Back up local/persistant data directory - save off to your smb share
* Following can all be done via Portainer UI!
* Stop container
* Remove container
* Stop stack
* Delete image (cause "latest" tag isn't used for some stupid reason!)
* Start stack (during this process new image will be downloaded and new container deployed)
* Please note: Compose script existing already in stack will have persistent local directory already mapped.  Kinda cool huh?
