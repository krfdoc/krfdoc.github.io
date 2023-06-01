---
title: Uptime Kuma
date: 2023-06-01 8:00:00 -0500
categories: [docker]
tags: [uptimekuma]
---

## Kuma Links --PENDING--NOT UPDATE YET AS YOU CAN SEE

[Dashy Mgmnt](https://github.com/Lissy93/dashy/blob/master/docs/management.md)

[Dashy Configuration](https://github.com/Lissy93/dashy/blob/master/docs/configuring.md)

[Dashy Website](https://dashy.to/)

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

> Figure out how to update dude and document!
{: .prompt-warning }