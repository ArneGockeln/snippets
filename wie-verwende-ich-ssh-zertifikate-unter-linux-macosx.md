---
title: "Wie verwende ich ssh Zertifikate unter linux und macosx?"
---
### Lokal
Als erstes erstellen wir uns ein Zertifikat auf unserer lokalen Maschine:

Der Aufruf generiert zwei Dateien unter `~/.ssh/`, einmal den privaten Schlüssel `id_rsa` und den öffentlichen Schlüssel `id_rsa.pub`.

<div class="alert alert-danger">
    <strong>Wichtig!</strong> Der private Schlüssel muss an einem sicherern Platz aufbewahrt werden!
</div>

```shell
$ ssh-keygen -t rsa
```

### Server
Als nächstes machen wir die entferne Maschine mit unserem Schlüssel bekannt, indem wir unseren öffentlichen Schlüssel in das .ssh Verzeichnis auf dem Server kopieren.

```shell
$ scp .ssh/id_rsa.pub user@servername:~/.ssh/
```

Dann fügen wir unseren öffentlichen Schlüssel der Datei ~/.ssh/authorized_keys auf unserem Server hinzu.

```shell
$ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
```

**Danach können wir den öffentlichen Schlüssel vom Server löschen.**

### Lokal
Auf unserer lokalen Maschine erstellen wir uns eine Konfigurationsdatei wo alle entfernten Maschinen eingetragen werden

```shell
$ touch ~/.ssh/config
```

Für jede entfernte Maschine tragen wir folgende Daten ein:

```shell
Host yourServername
User yourUsername
Port 22
HostName 192.168.10.2
```

Danach können wir uns dann wie folgt ganz einfach mit der entfernten Maschine verbinden:

```shell
$ ssh yourServername
```