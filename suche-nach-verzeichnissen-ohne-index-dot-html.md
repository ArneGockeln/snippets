---
title: "Suche nach Verzeichnissen, die keine index.html enthalten"
---
Mit folgendem Befehl werden alle Verzeichnisse unterhalb von ./ aufgelistet, die keine index.html Datei enthalten.

```shell
$ find . -depth -type d '!' -exec test -e "{}/index.html" ';' -print
```
