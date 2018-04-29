---
title: "Wie erstelle ich eine Dateiliste?"
---
Mit dem folgenden Aufruf werden alle Dateien im Verzeichnis templates/ aufgelistet und die Ausgabe des Terminals in eine Dateigeschrieben:

```shell
$ ls -p ./templates/ |grep -v / > liste.txt
```

- `ls -p ./templates/` liste alle Einträge des Verzeichnis ./templates auf und zeige ein / am Ende eines Verzeichnisses an
- `|grep -v /` ignoriere alle Einträge die auf ein / enden
- `> liste.txt` schreibe die Ausgabe in die Textdatei liste.txt im aktuellen Verzeichnis
