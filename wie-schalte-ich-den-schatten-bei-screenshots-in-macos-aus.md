---
title: "Wie schalte ich die Schatten bei Screenshots in MacOS aus?"
---
### Schatten deaktivieren

Terminal öffnen:

```
$ defaults write com.apple.screencapture disable-shadow -bool true
$ killall SystemUIServer
```

### Schatten aktivieren

Terminal öffnen:

```
$ defaults write com.apple.screencapture disable-shadow -bool false
$ killall SystemUIServer
```
