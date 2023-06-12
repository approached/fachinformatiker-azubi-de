---
title: SSH Tunnel
---

# SSH Tunnel

Beispiel:

`ssh user@testserver -L 1234:194.8.126.36:80`
`                       localport  ziel-ip : ziel-port`

Zugang zur mongo db tunneln:

`ssh root@testserver.com -L 1234:127.0.01:27017`
