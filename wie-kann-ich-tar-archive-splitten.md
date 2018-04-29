---
title: "Wie kann ich TAR Archive splitten?"
---
Um ein TAR Archiv in gleich große Teile zu teilen, ist dieser Befehl hilfreich:

```
tar cvzf - dir/ | split --bytes=200MB - backup.tar.gz.
```

Dabei gilt:

- `tar cvzf - dir/` packe das Verzeichnis `dir/`, mit Zip Komprimierung und zeige die zu packenden Dateien auf der Konsole an 
- `| split --bytes=200MB -` teile das Archiv in 200MB große Teile 
- `backup.tar.gz.` der Name des zu erzeugenden Archivs. Wichtig ist hier der Punkt am Ende. Für jeden einzelnen Teil wird automatisch ein Buchstabe angehängt. 

Unter MacOSX / macos kann der Befehl wie folgt abgeändert werden:

```
tar cvzf - dir/ | split -b 200m - backup.tar.gz.
```

Um die Archive wieder zu entpacken, ist folgender Befehl nötig:

```
cat backup.tar.gz.* | tar xzvf -
```

Dabei gilt:

- `cat backup.tar.gz.*` gebe den Inhalt auf der Konsole aus 
- `| tar xzvf -` leite die Ausgabe an tar weiter und extrahiere die Zip komprimierten Daten 