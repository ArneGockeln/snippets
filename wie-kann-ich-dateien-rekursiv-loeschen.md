---
title: "Wie kann ich Dateien rekursiv löschen?"
---
Der folgende Aufruf durchsucht das aktuelle, und alle untergeordneten, Verzeichnisse und löscht die gefundenen .meta Dateien.

```shell
$ find . -type f -name "*.meta" -exec rm {} \;
```

- `find .` finde Dateien im aktuellen Verzeichnis
- `-type f` finde nur Einträge vom Typ Datei
- `-name "*.meta"` finde Dateien mit der Endung .meta
- `-exec rm {} \;` lösche die gefundene Datei