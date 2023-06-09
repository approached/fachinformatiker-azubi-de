---
title: Nginx
description: 
published: true
date: 2022-02-09T13:12:35.485Z
tags: 
editor: markdown
dateCreated: 2022-02-09T13:12:33.852Z
---

# Nginx

Nginx ist ein Webserver genau wie der [Apache]. Es wird allerdings
Enige-X ausgesprochen.

## Konfiguration

Single Domain:

    server {
            server_name fachinformatiker-azubi.de;
            root /opt/sites/fachinformatiker-azubi.de;
            access_log /opt/logs/apache2/fachinformatiker-azubi.log;

            include global/mediawiki.conf;
            include global/php.conf;
    }

Default Settings in /etc/nginx/global/php.conf

    location ~ \.php$ {
            fastcgi_split_path_info ^(.+\.php)(/.+)$;
            fastcgi_pass unix:/var/run/php5-fpm.sock;
            fastcgi_index index.php;
            include fastcgi_params;
    }

    location ~ /\.ht {
            deny all;
    }

    gzip_static on;

    location = /favicon.ico {
            log_not_found off;
            access_log off;
    }

    location = /robots.txt {
            allow all;
            log_not_found off;
            access_log off;
    }

  [Apache]: Apache "wikilink"
  [Nginx ssl aktivieren]: Nginx_ssl_aktivieren "wikilink"
  [Nginx gzip aktivieren]: Nginx_gzip_aktivieren "wikilink"
  [Nginx cache aktivieren]: Nginx_cache_aktivieren "wikilink"
  
  ## Nginx ssl aktivieren
  
  Damit die richtigen Protokolle aktiviert sind wird empfohle folgende
Einstellung vorzunehmen:

        ssl_certificate /etc/ssl/example.com/example.pem;
        ssl_certificate_key /etc/ssl/example.com/example.key;

        ssl_protocols TLSv1.2 TLSv1.1 TLSv1;
        ssl_ciphers EECDH+AESGCM:EDH+AESGCM:EECDH:EDH:!MD5:!RC4:!LOW:!MEDIUM:!CAMELLIA:!ECDSA:!DES:!DSS:!3DES:!NULL;
        ssl_prefer_server_ciphers on;

        ssl_session_cache shared:SSL:10m;
        ssl_session_timeout 10m;
        
## Nginx gzip aktivieren

Das komprimierung **gzip** von [Nginx] aktivieren ist recht easy:

Datei editieren:

`vi /etc/nginx/nginx.conf `

Einfügen/ändern:

`       gzip on; `  
`       gzip_disable "msie6";`  
`   `  
`       gzip_comp_level 6;`  
`       gzip_min_length  1100;`  
`       gzip_buffers 16 8k; `  
`       gzip_proxied any;`  
`       gzip_types       text/plain application/xml text/css text/js text/xml application/x-javascript text/javascript application/javascript application/json    application/xml+rss;`

  [Nginx]: Nginx "wikilink"

## Nginx cache aktivieren

Diese Passagen einfügen unter der Site Configuration:

`vi /etc/nginx/conf.d/example.com.conf`

    # Javascript and CSS
    location ~* \.(?:css|js)$ {
      expires 2y; 
      access_log off;
      add_header Cache-Control "public";
    }

    # Media
    location ~* \.(?:jpg|jpeg|gif|png|ico|cur|gz|svg|svgz|mp4|ogg|ogv|webm|htc)$ {
      expires 1M; 
      access_log off;
      add_header Cache-Control "public";
    }