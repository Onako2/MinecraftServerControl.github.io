---
layout: default
title: SpigotMC
nav_order: 7
parent: Adjusting World & Server Properties
permalink: /docs/mscs/adjusting-world-server-properties/spigotmc
---

# SpigotMC

Installing [SpigotMC][spigotmc] is very similar to installing Forge.
Change to the `/opt/mscs/server/` directory, [download][download] the SpigotMC installer `BuildTools.jar`, and run the
following as the `minecraft` user (`sudo su minecraft`):

```bash
cd /opt/mscs/server
wget https://hub.spigotmc.org/jenkins/job/BuildTools/lastSuccessfulBuild/artifact/target/BuildTools.jar
java -jar BuildTools.jar
```

This will build the `spigot-X.X.X.jar` server file.

Create a new server (if necessary):

```bash
mscs create spigot 25565
```

`spigot` can be replaced with any name. Ensure that port `25565` is an unused port, or change it if nessessary.

This will create the directory `spigot` in `/opt/mscs/worlds` as well as the `server.properties` and `mscs.properties`
files:

Change the directory to the world that was created:

```bash
cd /opt/mscs/worlds/spigot
```

Modify the `mscs.properties` file and add/alter these lines, replacing versions and file paths as needed. You will need
to change the `mscs-server-jar` as a bare minimum:

```ini
mscs-client-version=1.8.7
mscs-server-version=1.8.7
mscs-server-jar=spigot-1.8.7.jar
mscs-server-url=
```

Start the server:

```bash
mscs start spigot
```

If the server fails to start, the `eula.txt` file may need to be edited and accepted:

```bash
editor /opt/mscs/worlds/spigot/eula.txt
```

The server should start up and run
The server startup can be monitored by running:

```bash
mscs console spigot
```

Once you are done watching the server boot up, you can press `<Ctrl-D>` to detach.

Simply add plugins as you would normally by dragging them into the `/opt/mscs/worlds/spigot/plugins` folder,
assuming `spigot` is the name of your world.

[spigotmc]: https://www.spigotmc.org/wiki/spigot/
[download]: https://hub.spigotmc.org/jenkins/job/BuildTools/
