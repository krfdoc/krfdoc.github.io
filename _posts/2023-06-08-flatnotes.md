---
title: Flatnotes
date: 2023-06-08 9:00:00 -0500
categories: [docker]
tags: [markdown]
---



[Github Page](https://github.com/Dullage/flatnotes)

## Docker Compose

### Example Template

```terminal
version: "3"

services:
  flatnotes:
    container_name: flatnotes
    image: dullage/flatnotes:latest
    environment:
      PUID: 1000
      GUID: 1000
      FLATNOTES_AUTH_TYPE: "password"
      FLATNOTES_USERNAME: "user"
      FLATNOTES_PASSWORD: "changeMe!"
      FLATNOTES_SECRET_KEY: "aLongRandomSeriesOfCharacters"
    volumes:
      - "./data:/data"
      # Optional. Allows you to save the search index in a different location: 
      # - "./index:/data/.flatnotes"
    ports:
      - "8080:8080"
    restart: unless-stopped
```

### KRF Custom Template

```terminal
custom goes here
```