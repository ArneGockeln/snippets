---
title: "Wie suche ich rekursiv nach Dateien von einer Liste?"
---
Zunächst brauchen wir eine Liste mit Dateinamen. Wie man die erstellt steht [>>hier<<](#wie-erstelle-ich-eine-dateiliste).

Unsere Liste sieht so aus:

```shell
attachment_change.twig
base.twig
bugs.twig
bugs_change.twig
comment_change.twig
index.twig
```

Mit folgendem Aufruf wird der Inhalt der Datei liste.txt ausgegeben und jeder Eintrag ausgehend vom aktuellen Verzeichnis gesucht.

```shell
$ cat liste.txt |while read file; do find . -name "$file"; done
```

- `cat liste.txt` zeige den Inhalt der Datei liste.txt
- `|while read file;` lese den Inhalt einer Zeile und weise ihn der Variable file zu
- `do find . -name "$file"; done` ausgehend vom aktuellen Verzeichnis suche nach dem Dateinamen in $file

### Beispiel:

```shell
$ cat liste.txt |while read file; do find . -name "$file"; done
./templates/attachment_change.twig
./templates/base.twig
./templates/bugs.twig
./templates/bugs_change.twig
./templates/comment_change.twig
./templates/index.twig
```

Die Ausgabe kann natürlich auch in eine Datei umgeleitet werden.

```shell
$ cat liste.txt |while read file; do find . -name "$file"; done > neue_liste.txt
```