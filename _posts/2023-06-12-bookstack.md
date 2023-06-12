---
title: BookStack
date: 2023-06-12 9:30:00 -0500
categories: [docker]
tags: [bookstack,markdown]
---


[Home Page](https://www.bookstackapp.com/)

[Github Page](https://github.com/linuxserver/docker-bookstack)

[Docker Hub](https://hub.docker.com/r/linuxserver/bookstack)

## Docker Compose

### Example Template

```terminal
---
version: "2"
services:
  bookstack:
    image: lscr.io/linuxserver/bookstack
    container_name: bookstack
    environment:
      - PUID=1000
      - PGID=1000
      - APP_URL=https://bookstack.example.com
      - DB_HOST=bookstack_db
      - DB_PORT=3306
      - DB_USER=bookstack
      - DB_PASS=<yourdbpass>
      - DB_DATABASE=bookstackapp
    volumes:
      - ./bookstack_app_data:/config
    ports:
      - 6875:80
    restart: unless-stopped
    depends_on:
      - bookstack_db
  bookstack_db:
    image: lscr.io/linuxserver/mariadb
    container_name: bookstack_db
    environment:
      - PUID=1000
      - PGID=1000
      - MYSQL_ROOT_PASSWORD=<yourdbpass>
      - TZ=Europe/London
      - MYSQL_DATABASE=bookstackapp
      - MYSQL_USER=bookstack
      - MYSQL_PASSWORD=<yourdbpass>
    volumes:
      - ./bookstack_db_data:/config
    restart: unless-stopped
```

### KRF Custom Template