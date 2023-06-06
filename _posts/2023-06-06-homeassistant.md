---
title: Home Assistant
date: 2023-06-06 8:00:00 -0500
categories: [homeassistant]
tags: [homeassistant,docker]
---

## Install Home Assistant

[Home Assistant Installation](https://www.home-assistant.io/installation/linux)


### Docker Compose


* Default Compose File
```terminal
version: '3'
services:
  homeassistant:
    container_name: homeassistant
    image: "ghcr.io/home-assistant/home-assistant:stable"
    volumes:
      - /PATH_TO_YOUR_CONFIG:/config
      - /etc/localtime:/etc/localtime:ro
    restart: unless-stopped
    privileged: true
    network_mode: host
```

* KRF Custom Compose File
```terminal
version: '3'
services:
  homeassistant:
    container_name: homeassistant
    image: "ghcr.io/home-assistant/home-assistant:stable"
    volumes:
      - /home/krf/docker_volumes/homeassistant:/config
      - /etc/localtime:/etc/localtime:ro
    restart: unless-stopped
    privileged: true
    network_mode: host
    ```