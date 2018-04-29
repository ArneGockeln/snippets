---
title: "Wie kann ich den DNS Cache leeren?"
---
### OSX 10.10
```
$ sudo discoveryutil udnsflushcaches
```

### OSX 10.9
```
$ dscacheutil -flushcache; sudo killall -HUP mDNSResponder
```

### OSX 10.7  – 10.8
```
$ sudo killall -HUP mDNSResponder
```

### OSX 10.5 – 10.6
```
$ sudo dscacheutil -flushcache
```

### Windows
```
$ ipconfig /flushdns
```

### Linux (depending on what you’re running)
```
$ /etc/init.d/named restart
$ /etc/init.d/nscd restart
```