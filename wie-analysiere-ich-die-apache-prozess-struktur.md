---
title: "Wie analysiere ich die apache prozess struktur?"
---
Wer Apache Webserver administriert will auch wissen welche Prozesse gestorben sind bzw. welche Prozesse einen hohen Speicherverbrauch aufweisen.

Zunächst müssen wir die Prozess ID herausfinden:

```shell
$ lsof -i :80
```

- `lsof -i` zeige alle aktiven Internet Prozesse
- `:80` filtere nur die Prozesse die auf Port 80 lauschen

### Beispiel:

```shell
$ lsof -i :80
COMMAND PID USER FD TYPE DEVICE SIZE/OFF NODE NAME
apache2 1291 root 3u IPv4 13374 0t0 TCP *:http (LISTEN)
apache2 11661 www-data 3u IPv4 13374 0t0 TCP *:http (LISTEN)
apache2 11795 www-data 3u IPv4 13374 0t0 TCP *:http (LISTEN)
```

`11661` ist die gesuchte Prozess ID.

Als nächstes schreiben wir eine Logdatei mit Statistiken über diesen Prozess:

<div class="alert alert-danger">
    <strong>Wichtiger Hinweis:</strong> Die Größe der Logdatei kann sehr schnell anwachsen. Der Prozess strace sollte nach wenigen Sekunden mittels STRG+C abgebrochen werden!
</div>

```shell
$ strace -p11661 -e trace=file -o /tmp/strace.log
```
