---
title: Traefik
---

# Traefik

Traefik ist ein Proxy mit vielen Features. Das Tool setzt man vorallem ein wenn man mit Docker oder Kubernetes arbeitet. Man kann damit die Request sehr gut weiterleiten und es verarbeiten. Ein weiterer Vorteil den Traefik mit sich bringt, ist das Automatische erstellen von Let's Encrypt SSL Zertifikate. Dadurch werden die Zertifkate automitsch generiert und gemanaged von Traefik und man muss keine Einstellungen dafür vornehmen.

## Installieren

Der Einfachste start mit Traefik ist es eine `docker-compose.yml` Datei zu erstellen. Wenn man die Docker Compose Datei startet lässt sich das Webinterface aufrufen via `traefik.example.com`. Im nächsten Schritt kann man nun Services (z.B. Webserver) anbinden.

```yml
---
version: "3.8"

services:
  traefik:
    image: traefik:latest
    container_name: traefik
    volumes:
      - ./letsencrypt:/letsencrypt
      - /var/run/docker.sock:/var/run/docker.sock:ro
    labels:
      traefik.enable: true
      traefik.http.routers.api.entryPoints: https
      traefik.http.routers.api.rule: Host(`traefik.example.com`) # Change domain
      traefik.http.routers.api.service: api@internal
      traefik.http.routers.api.tls: true
      traefik.http.routers.api.tls.certresolver: lets
    command:
      - '--api'
      - '--providers.docker=true'
      - '--providers.docker.network=traefik_proxy'
      - '--providers.docker.exposedByDefault=false'
      - '--entrypoints.http=true'
      - '--entrypoints.http.address=:80'
      - '--entrypoints.https=true'
      - '--entrypoints.https.address=:443'
      - '--log=true'
      - '--log.level=DEBUG'
      - '--log.filepath=/var/log/traefik.log'
      - '--certificatesresolvers.lets.acme.httpchallenge=true'
      - '--certificatesresolvers.lets.acme.httpchallenge.entrypoint=http'
      - '--certificatesresolvers.lets.acme.email=traefik@example.com'  # Change domain
      - '--certificatesresolvers.lets.acme.storage=/letsencrypt/acme.json'
      - '--log.filePath=/dev/stdout'
      - '--log.level=ERROR'
    networks:
      - traefik_proxy
    ports:
      - 80:80
      - 443:443
    restart: always

networks:
  traefik_proxy:
    name: traefik_proxy
```

Um einen Service einzubinden erstellt man einen weietere `docker-compose.yml` Datei und startet es. Die Anwendung sollte nun im Webinterface von Traefik zu sehen sein.
```yml
---
version: "3.8"

services:
  alcodo_com:
    image: nginx:alpine
    container_name: example.com
    restart: always
    volumes:
      - ./content:/usr/share/nginx/html:ro
    labels:
      traefik.enable: true
      traefik.http.routers.example.entrypoints: https
      traefik.http.routers.example.rule: Host(`example.com`)
      traefik.http.routers.example.tls: true
      traefik.http.routers.example.tls.certresolver: lets
    networks:
      - traefik_proxy

networks:
  traefik_proxy:
      name: traefik_proxy
```
