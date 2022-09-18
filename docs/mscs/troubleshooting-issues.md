---
layout: default
title: Troubleshooting/Issues
nav_order: 10
permalink: /docs/mscs/troubleshooting-issues
---

# Troubleshooting

## Permission denied error
If you get a `permission denied` error when attempting to run a `mscs` command, please ensure that the `minecraft` user
has the correct permissions set:

```bash
chmod -R u+w /opt/mscs
chown -R minecraft:minecraft /opt/mscs
```

## Error starting the server: couldn't retrieve the server's process ID
This is usually due to an outdated java installation on your machine when trying to start the minecraft server. Verify that the java version required for your minecraft server version is installed on your machine.

---

# Issues

We have only tested this code in a Debian/Ubuntu environment, but there is no reason that it shouldn't work in any
appropriately configured UNIX-like environment, including Apple Mac OSX and the other BSD variants, with only minor
modifications. If you experience errors running this script, please post a copy of the error message and a note
detailing the operating environment where the error occurs to the support thread, and we will try to work out a
solution with you

For a list of current and past issues, or to submit an issue or question you have, please visit the
[Github issues page][mscs_issues].

## Overviewer Bug Note

Aas of May 2020, there is a bug in Overviewer that occurs in certain system installations that have
multiple Minecraft versions located in the `/opt/mscs/.minecraft/versions` folder. In systems with this bug, the
`mscs map` command will hang and mapping will never complete (see [Issue #238][map_issue]).
If running the `mscs map` command hangs and never completes, and you have multiple versions of minecraft located in the
`/opt/mscs/.minecraft/versions` folder, please try deleting all versions except the version that you need for your world
and attempt mapping again. If you're still having issues, [please submit an issue on Github][mscs_issues].

[map_issue]: https://github.com/MinecraftServerControl/mscs/issues/238
[mscs_issues]: https://github.com/MinecraftServerControl/mscs/issues/
