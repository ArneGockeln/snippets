---
title: "Wie richte ich eine IP Sperre für WordPress Permalink Pfade ein?"
---
Der Pfad `http://domain.de/hidden` soll nur für bestimmte IPs freigegeben werden. Dazu wird die `.htaccess` im WordPress Document Root bearbeitet und direkt als oberster Stelle wie folgt eingefügt:

```shell
# block access to /start permalink for every ip except the ones in list
RewriteBase /
RewriteCond %{REQUEST_URI} ^/hidden
RewriteCond %{REMOTE_ADDR} !^192.168.0.10$
RewriteRule .* - [F]
```

Die IP 192.168.0.10 ist jetzt die einzige IP die Zugriff auf `http://domain.de/hidden` hat.
