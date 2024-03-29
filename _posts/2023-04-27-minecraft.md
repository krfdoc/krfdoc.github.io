---
title: Minecraft
date: 2023-04-27 8:00:00 -0500
categories: [minecraft]
tags: [minecraft,seeds,seed-maps,minecraft-server]
---

## Minecraft

### Personal Seed Maps
* [KRF's Seed Map](https://www.chunkbase.com/apps/seed-map#-1182128540532934599)
* [SURVIVAL-Lew and Dad's Seed Map](https://www.chunkbase.com/apps/seed-map#-7871458779404887414)
* [CREATIVE-Lew's Seed Map](https://www.chunkbase.com/apps/seed-map#-6953476837232445004)

### Custom Server Script
Located at `/home/krf/`
* start server
```terminal
sudo ./start.sh
```
Need to be in home directory where .jar file is located

* or run the original (default) start-up script:
```terminal
sudo java -Xms4G -Xmx6G -jar server.jar nogui
```
* Here's your custom start script named "start.sh"
```terminal
#!/bin/sh
cd "$(dirname "$0")"
exec java -Xms4G -Xmx6G -jar server.jar --nogui
```

* Once minecraft server is running (you can tell from the XCP-ng terminal), just type `stop` then `enter`

### To create new world
User "mv" cli command to rename "world" folder.  New world is automatically created upon next server boot

### Other server commands (while server is running)
```terminal
/seed

/weather clear

/spawnpoint #sets the spawn point for a player

/stop #stops server

/gamemode creative #maybe "c" has to be capitalized?

/op Valridge #to grant user "Valridge" operater rights.  

/deop Valridge #remove rights
```

### Client (not server!) hotkeys and commands

/ #to open up chat (also prefixes the required forward slash)

/tp <player> <target> #teleport player to target.  UN works for player...does UN work for target?

"f3" button = get coordinates

### Terminal operability with "screen" package installed.
More testing needs to be done to finish documentation
```terminal
screen <then hit spacebar>
sudo java -Xms4G -Xmx6G -jar server.jar nogui

You can press Ctrl+A+D to detach from this Screen session, which will place you back into the original terminal session you had while leaving Minecraft running inside the detached screen. 
You can log out without stopping the process or use screen -r to reattach it and bring it back to the foreground.
```
### How to Setup a Server

* `https://minecraft.fandom.com/wiki/Tutorials/Setting_up_a_server`

* Note that you're basically creating a minecraft folder in your home directory (just use your home directory btw!  It'll be easier) and then putting the server.jar file in there.  Then run with the script or custom startup script.  Remember you will have to nano into the EULA to accept, and you probably want to go through the config file and make sure settings are correct.  `Don't forget to add your Seed ID before you start it! (optional, but cool if you want a nice map-spawn point)`  Configs/Settings are in `server.properties`

* After that you have to assign execution permissions for the script(s). You do that with the following command:

```terminal
chmod +x start.sh
```

### To Update

* Just replace the Java .jar file (usually named "server.jar", but can really be anything as long as it matches your start script) with the new one downloaded from here: `https://www.minecraft.net/en-us/download/server`


* Simple as that.  Also a good idea to update the Ubuntu server while you're at it.  Feel free to archive off a version of the old Server.jar java file, but since there's no customizations within the .jar file itself, it shouldn't be a deal breaker