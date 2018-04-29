---
title: "Mac OS FTP Server starten"
---
Mit diesem Befehl kann man den FTP Server von Mac OS starten:

```shell
$ sudo -s launchctl load -w /System/Library/LaunchDaemons/ftp.plist
```

Mit diesem Befehl kann man den FTP Server von Mac OS beenden:

```shell
$ sudo -s launchctl unload -w /System/Library/LaunchDaemons/ftp.plist 
```

Wenn der FTP Server läuft, kann man sich mit dem Benutzernamen und Passwort der vorhandenen Accounts anmelden und auf das jeweilige Home Verzeichnis zugreifen.

```shell
$ ftp://user@localhost
```