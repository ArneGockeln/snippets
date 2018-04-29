---
title: "Wie verwende ich tar mit Dateilisten?"
---
Gerade wenn ich Backups erstelle ist es sehr nützlich nur bestimmte Dateien von einer Dateiliste in ein Tar Archiv zu packen.

Als erstes brauchen wir eine Dateiliste. Wie man die erstellt steht [>>hier<<](#wie-erstelle-ich-eine-dateiliste). Hier will ich nur die PHP Dateien im aktuellen Verzeichnis packen.

```shell
$ ls -1 *.php > phpdateien.txt
```

Dann packen wir alle Dateien von der Liste in ein Archiv und komprimieren es auch gleich.

```shell
$ tar -cvz -T phpdateien.txt -f archiv.tar.gz
a config.php
a index.php
```

- `tar -cvz` erstelle ein Tar Archiv (c), zeige die hinzugefügten Dateien an (v) und komprimiere anschließend mit gzip (z)
- `-T phpdateien.txt` verwende nur die Dateien aus der Dateiliste phpdateien.txt
- `-f archiv.tar.gz` erstelle die Archivdatei archiv.tar.gz