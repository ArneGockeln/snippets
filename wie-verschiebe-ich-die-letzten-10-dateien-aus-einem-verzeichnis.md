---
title: "Wie verschiebe ich die letzten 10 Dateien aus einem Verzeichnis?"
---
In einem Verzeichnis sind mehr als 100 XML Dateien vorhanden. Ich möchte jetzt nur die letzten 10 XML-Dateien in ein anderes Verzeichnis verschieben. Das geht mit einem Einzeiler:

```shell
$ for file in $(ls -p *.xml|grep -v /|tail -10); do mv $file ./tmp/; done;
```

- `for file in` die Variable $file festlegen und für jeden Treffer befüllen
- `$(ls -p *.xml|grep -v /|tail -10);` alle xml Dateien auflisten, 1 Treffer pro Zeile, auf die letzten 10 Treffer beschränken
- `do mv $file ./tmp/` jeden Treffer in $file nach ./tmp/ verschieben
- `done;` for Schleife beenden
