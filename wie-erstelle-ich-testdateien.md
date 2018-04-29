---
title: "Wie erstelle ich Testdateien?"
---
Mittels 'dd' können wir Testdateien mit beliebiger Dateigröße erstellen. In diesem Beispiel erstelle ich eine 100 MB Testdatei.

```shell
$ dd if=/dev/random of=./filename bs=512 count=204800
```

Die Größe der Datei wird nach folgender Formel berechnet:

- 100 MB = (100*1024*1024) / 512 = 204800
- bs = 512
- count = 204800

<div class="alert alert-warning">
    <strong>Hinweis:</strong> Testdateien im Gigabyte Bereich können sehr lange dauern um erstellt zu werden. Das ist auch abhängig von der Lese-/Schreibgeschwindigkeit der Festplatte.
</div>

### Beispiel:

```shell
$ dd if=/dev/random of=./testdatei bs=512 count=204800
204800+0 records in
204800+0 records out
104857600 bytes transferred in 7.431913 secs (14109099 bytes/sec)

$ ls -lah testdatei
-rw-r--r--  1 arnegockeln  staff   100M 31 Okt 11:28 testdatei
```
