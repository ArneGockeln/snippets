---
title: "Wie durchsuche ich Quelltext nach String vorkommen mit Zeilennummer?"
---
Wir suchen nach PHP Konstanten innerhalb eines Verzeichnisses und wollen die Datei mit Zeilennummer ausgeben:

```shell
$ grep -Rn --exclude-dir=routes PB_ROOT* ./includes |awk -F: '{print $1"::"$2}'
```

- `grep -Rn` durchsuche rekursiv und zeige Zeilennummern an
- `--exclude-dir=routes` ignoriere das Verzeichnis routes/
- `PB_ROOT*` der Name der Konstante beginnend mit PB_ROOT...
- `./includes` das Verzeichnis das rekursiv durchsucht werden soll
- `|awk -F: '{print $1"::"$2}'` mittels awk formatieren wir die Ausgabe um ins Format &lt;dateipfad&gt;::&lt;zeilennummer&gt;

### Beispiel:

```shell
$ grep -Rn --exclude-dir=routes PB_ROOT* ./includes |awk -F: '{print $1"::"$2}'
./includes/app_top.php::34
./includes/app_top.php::36
./includes/app_top.php::37
./includes/app_top.php::44
./includes/app_top.php::47
./includes/core/functions.php::15
./includes/core/functions.php::16
```