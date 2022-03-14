---
id: bv0x156h0li6iiiy10guwcp
title: Displaying Native Gui Notifications from Bash
desc: ''
updated: 1647279164889
created: 1647279141038
---

## Linux

```bash
#!/bin/bash
sleep 10
notify-send "notify.sh" "Task #1 was completed successfully"
```

OSX

```bash
#!/bin/bash
sleep 10
osascript -e "display notification \"Task #1 was completed successfully\" with title \"notify.sh\""
```
