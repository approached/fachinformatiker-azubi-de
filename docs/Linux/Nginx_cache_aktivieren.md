---
title: Nginx cache aktivieren
---

# Nginx cache aktivieren

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
