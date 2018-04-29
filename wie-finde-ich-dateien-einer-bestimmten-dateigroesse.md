---
title: "Wie finde ich Dateien einer bestimmten Dateigrösse?"
---
Der folgende Befehl durchsucht das Verzeichnis ./uploads/ nach Dateien, die größer als 500kb sind und listet diese, inkl. der tatsächlichen Größe und des Verzeichnis Pfads, auf.

```shell
$ find ./uploads -type f -size +500k -exec ls -lh {} \; |awk '{ print $5 ": " $9 }';
```

Sollen Dateien kleiner als 500kb angezeigt werden, so wird das + in ein - geändert. In dem Beispiel also `-size -500k`.

- `find ./uploads` finde Dateien innerhalb des Verzeichnis ./uploads
- `-type f` liste nur Dateien auf, ignoriere Verzeichnisse
- `-size +500k` liste nur Dateien auf, die größer als 500 KB sind
- `-exec ls -lh {} \;` führe den Befehl ls -lh aus
- `|awk '{ print $5 ": " $9 }';` die Ausgabe von -exec wird mittels awk geparsed und die Inhalte der Spalten 5 und 9 ausgegeben

### Beispiel

```shell
$ find ./uploads -type f -size +500k -exec ls -lh {} \; |awk '{ print $5 ": " $9 }';
1,0M: ./uploads/2014/03/Sequence-01_1.mp4
520K: ./uploads/2014/05/slide-transport-1-1024x442.png
589K: ./uploads/2014/05/slide-transport-1-1120x450.png
621K: ./uploads/2014/05/slide-transport-1-1120x480.png
575K: ./uploads/2014/05/slide-transport-1-960x483.png
554K: ./uploads/2014/05/slide-wedding-bg.png
1,6M: ./uploads/2014/06/agency_video.mp4
```