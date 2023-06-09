---
title: Flatnotes
date: 2023-06-08 9:00:00 -0500
categories: [docker]
tags: [flatnotes,markdown]
---



[Github Page](https://github.com/Dullage/flatnotes)

[DBTech's Install Video](https://www.youtube.com/watch?v=1e2yGEFaB0A)

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

> `AUTH_TYPE` can be "none", "password", or "TOTP"
{: .prompt-info }

### KRF Custom Template

```terminal
version: "3"

services:
  flatnotes:
    container_name: flatnotes
    image: dullage/flatnotes:latest
    environment:
      PUID: 1000
      GUID: 1000
      # AUTH_TYPE can be "none", "password", or "TOTP"
      FLATNOTES_AUTH_TYPE: "password"
      # If "totp" is used, activate following line & insert 32 char string
      # FLATNOTES_TOTP_KEY: "123abc..."
      FLATNOTES_USERNAME: "krf"
      FLATNOTES_PASSWORD: "password"
      FLATNOTES_SECRET_KEY: "aLongRandomSeriesOfCharacters"
    volumes:
      - "/home/krf/docker_volumes/flatnotes:/data"
      # Optional. Allows you to save the search index in a different location: 
      # - "./index:/data/.flatnotes"
    ports:
      - "7475:8080" # change first set to whatever you need
    restart: unless-stopped
```

> AUTH_TYPE: "password" will litterally make your password = password!  There is no way to change it in the application!
{: .prompt-danger }