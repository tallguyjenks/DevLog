---
id: hm181qra1we28l5hxjr44lh
title: Multiprocessing in Bash Scripts
desc: ''
updated: 1647279210487
created: 1647279181258
---

```bash
#!/bin/bash
function task1() {
    echo "Running task1..."
    sleep 5
}
function task2() {
    echo "Running task2..."
    sleep 5
}
task1 &
task2 &
wait
echo "All done!"
```

the `wait` builtin makes sure that all background processes have completed before carrying on
