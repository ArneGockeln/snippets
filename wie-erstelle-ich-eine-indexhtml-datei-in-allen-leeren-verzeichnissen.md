---
title: "Wie erstelle ich eine index.html Datei, in allen leeren Verzeichnissen?"
---

Mit folgendem Befehl durchsuche ich alle Verzeichnisse unterhalb von ./ und erstelle in jedem Verzeichnis eine index.html Datei, in dem sich **keine** index.html Datei befindet.

```shell
$ find . -depth -type d '!' -exec test -e "{}/index.html" ';' -print|while read f; do touch "$f/index.html"; done
```

Die Datei wäre im obigen Fall leer. Der Befehl kann wie folgt erweitert werden:

```shell
$ find . -depth -type d '!' -exec test -e "{}/index.html" ';' -print|while read f; do echo '<!DOCTYPE html><html><head><meta http-equiv="refresh" content="0;url=/index.html" /></head><body></body></html>' > "$f/index.html"; done
```

Es wird immer noch in allen leeren Verzeichnissen eine index.html erstellt, allerdings mit dem Inhalt:

```html 
<!DOCTYPE html><html><head></head><body><meta http-equiv="refresh" content="0;url=/index.html" /></body></html>
```

Das bewirkt eine direkte Weiterleitung nach http://baseurl.de/index.html. Ich verwende diesen Befehl um leere Verzeichnisse auf meinem Webserver zu füllen.
