---
title: Curl
description: 
published: true
date: 2022-02-16T21:46:16.276Z
tags: 
editor: markdown
dateCreated: 2022-02-16T21:46:15.224Z
---

# Curl

```
Get:
curl -X GET http://fachinformatiker-azubi.de/rest/

Verbose:
curl -v -X GET http://fachinformatiker-azubi.de/rest/

Htaccess:
curl -u "user:pass" -v -X GET http://fachinformatiker-azubi.de/rest/

Post:
curl -X POST --verbose --data "text=BLA&filename=angebotsliste.pdf" --data "content=@base64_encode.txt" http://fachinformatiker-azubi.de/mailer.php
```