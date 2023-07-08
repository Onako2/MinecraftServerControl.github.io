---
layout: default
title: Backups
nav_order: 5
permalink: /docs/mscs/backups
---

# Backups
{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Using Backup

To backup:

```bash
mscs backup <world>
```

Where `<world>` is the world to backup. Leaving `<world>` off will back up all worlds.

By default, backups are saved in `/opt/mscs/backups`. The location backups are saved can be configured by changing
`mscs-backup-location` in `mscs.defaults` or the world's `mscs.properties` config file
(See [Adjusting World & Server Properties](adjusting-world-server-properties)).

## Scheduling Backups

To schedule backups so they run periodically, please see [scheduling tasks](scheduling-tasks).

## Cleaning Backups

Backups are automatically cleaned whenever a backup runs.

You can manually clean up the backups created by running the `mscs clean-backups` command.

## Viewing & Restoring Backups

You can view the backups created by running the `mscs list-backups` command, and restore a backup using the
`mscs restore-backup` command.

You can specify how long to keep backups by changing the `mscs-backup-duration` property in `mscs.defaults` or the
world's `mscs.properties` config file (see [Adjusting World & Server Properties](adjusting-world-server-properties)).

### Restoring Backup Example

To list the date and time of all available backups for a world named `alpha`:

```bash
mscs list-backups alpha
```

To restore a specific backup for `alpha`:

```bash
mscs restore-backup alpha 2015-03-25T21:15:11-06:00
```
