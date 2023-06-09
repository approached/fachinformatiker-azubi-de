---
title: Docker
description: 
published: true
date: 2022-03-16T11:09:22.668Z
tags: 
editor: markdown
dateCreated: 2022-03-16T10:45:32.653Z
---

# Docker

Mithilfe von Docker kann man mit dem Betriebssystem, Performante Virtualiserungen betreiben.

## Logs

Aktive container anzeigen:
```
docker ps

CONTAINER ID   IMAGE COMMAND                  CREATED       STATUS                    NAMES
950b39e79e8b   redis:alpine "docker-entrypoint.s…"   7 weeks ago   Up 41 hours        redis
```

Logs anzeigen:
```
docker logs 950b39e79e8b

or

docker logs redis
```

Letzte 20 Zeilen anzeigen:
```
docker logs redis -n 20
```

Logs verfolgen:
```
docker logs redis -f
```