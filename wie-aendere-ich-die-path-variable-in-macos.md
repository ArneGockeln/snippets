---
title: "Wie ändere ich die PATH Variable in MacOS?"
---
Im Benutzerverzeichnis gibt es die Datei `.bash_profile`. Darin werden persönliche Einstellungen vorgenommen.

```
$ nano ~/.bash_profile
```

Dort dann wie folgt den Pfad anpassen. In meinem Fall füge ich den Pfad zu meiner Qt Installation hinzu `/Users/arnegockeln/Sourcecode/SDKs/Qt/5.9.1/clang_64/bin`

```
export PATH=$PATH:/Users/arnegockeln/Sourcecode/SDKs/Qt/5.9.1/clang_64/bin
```

Die Datei speichern und anschließend dem Terminal mitteilen dass sich etwas geändert hat.

```
$ source ~/.bash_profile
```

Mit echo dann die Variable überprüfen

```
$ echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Users/arnegockeln/Sourcecode/SDKs/Qt/5.9.1/clang_64/bin
```
