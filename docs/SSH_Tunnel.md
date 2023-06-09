---
title: SSH Tunnel
description: 
published: true
date: 2022-02-16T21:41:40.229Z
tags: 
editor: markdown
dateCreated: 2022-02-16T21:41:39.133Z
---

# SSH Tunnel

Beispiel:

`ssh user@testserver -L 1234:194.8.126.36:80`  
`                       localport  ziel-ip : ziel-port`

Zugang zur mongo db tunneln:

`ssh root@testserver.com -L 1234:127.0.01:27017`