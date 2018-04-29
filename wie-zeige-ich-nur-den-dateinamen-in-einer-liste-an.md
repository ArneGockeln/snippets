---
title: "Wie zeige ich nur den Dateinamen in einer Liste an?"
---
Mit dem folgenden Aufruf werden nur die Dateinamen in einem Verzeichnis aufgelistet.

```shell
$ ls -1 ./templates
```

- `ls -1` liste nur die Datei- und Verzeichnisnamen auf
- `./templates` alle Dateien im Verzeichnis templates`

### Beispiel:

```shell
$ ls -1 ./templates/
attachment_change.twig
base.twig
bugs.twig
bugs_change.twig
comment_change.twig
css
fonts
img
index.twig
js
```