---
title: SpeedTest Tracker
date: 2023-06-12 11:00:00 -0500
categories: [docker]
tags: [speedtest,markdown]
---



[Github Page](https://github.com/alexjustesen/speedtest-tracker)

[Home Page](https://docs.speedtest-tracker.dev/)

## Docker Compose

### Example Template

```terminal
version: '3.3'
services:
    speedtest-tracker:
        container_name: speedtest-tracker
        ports:
            - '8080:80'
            - '8443:443'
        environment:
            - PUID=1000
            - PGID=1000
        volumes:
            - '/path/to/directory:/config'
            - '/path/to/directory/web:/etc/ssl/web'
        image: 'ghcr.io/alexjustesen/speedtest-tracker:latest'
        restart: unless-stopped
```

### KRF Custom Template

```terminal
version: '3.3'
services:
    speedtest-tracker:
        container_name: speedtest-tracker
        ports:
            - '8080:80'
            - '8443:443'
        environment:
            - PUID=1000
            - PGID=1000
        volumes:
            - '/home/krf/docker_volumes/speedtest:/config'
            - '/home/krf/docker_volumes/speedtest/web:/etc/ssl/web'
        image: 'ghcr.io/alexjustesen/speedtest-tracker:latest'
        restart: unless-stopped
```

> extra box yo
{: .prompt-danger }