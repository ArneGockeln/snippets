---
title: "Suche nach einem String und zähle das Ergebnis"
---
Mit folgendem Konsolenaufruf kann nach einem String in einem Verzeichnis gesucht werden. Dabei werden die angegebenen Gitrepositories ignoriert und das Ergebnis gezählt.

```shell
$ grep -H -r "SELECT" ./includes |cut -d: -f1 |grep -v "\.git/*" |nl
```

- `SELECT` ist der gesuchte String
- `./includes` ist das zu durchsuchende Verzeichnis
- `|cut -d: -f1` schneidet die Dateinamen ab
- `|grep -v "\.git/*"` exkludiert das Verzeichnis .git
- `|nl` zählt die Zeilen und gibt vor jeder Zeile die Zahl aus

### Beispiel:

```shell
$ grep -H -r "SELECT" ./includes |cut -d: -f1 |grep -v "\.git/*" |nl
1	./includes/core/Attachment.php
2	./includes/core/Bug.php
3	./includes/core/BugMetaManager.php
4	./includes/core/Comment.php
5	./includes/core/Database.php
6	./includes/core/Database.php
7	./includes/core/Database.php
8	./includes/core/Database.php
9	./includes/core/Project.php
10	./includes/core/ProjectMeta.php
11	./includes/core/User.php
```