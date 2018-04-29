---
title: "Wie konvertiere ich einen putty-key in das ssh Format?"
---
Als erstes müssen wir die Putty Tools installieren, falls noch nicht vorhanden.

<div class="alert alert-warning">
    <strong>Hinweis für Mac OSX Nutzer</strong> Es gibt ein fertig kompiliertes Binary unter <a href="https://github.com/eldridgegreg/puttygen-osx" target="_blank">https://github.com/eldridgegreg/puttygen-osx</a>. Alternativ können die Putty Tools auch über Mac Ports installiert werden.
</div>

```shell
$ aptitude install putty-tools
```

Dann können wir den privaten Putty Schlüssel nach openSSH konvertieren:

```shell
$ puttygen mykey.ppk -O private-openssh -o mykey.openssh
```

Und abschließend konvertieren wir noch den öffentlichen Putty Schlüssel nach openSSH:

```shell
$ puttygen mykey.ppk -O public-openssh -o my_public_key.openssh
```
