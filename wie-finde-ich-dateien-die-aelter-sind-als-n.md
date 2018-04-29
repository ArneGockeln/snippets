---
title: "Wie finde ich Dateien und Verzeichnisse die älter sind als N"
---
Der folgende Befehl findet alle Verzeichnisse, die nicht älter sind als 2 Tage:

```
find . -type d -mtime 1 -mtime -2 -daystart
```

Das gleiche kann natürlich auch auf Dateien angewendet werden:

```
find . -type f -mtime 1 -mtime -2 -daystart
```

Dabei gilt:

- `find . -type d` finde alle Verzeichnisse oder `find . -type f` finde alle Dateien im aktuellen Verzeichnis
- `-mtime 1` mit aktuellem Zeitwert
- `-mtime -2` maximal 2 Tage zurück
