---
id: s9be739huuriwbjd0jxn4j3
title: Qrcode
desc: ''
updated: 1641168469942
created: 1641105063864
stub: false
isDir: false
---


```python
import qrcode
img = qrcode.make('https://www.bryanjenks.dev')
img.save("some_file.png")
```

had to `pip install qrcode`  and also a package dependency `pip install Image`
produced this image, which when scanned goes to the the URL:

![alt](assets/images/Pasted_image_20211103105409.png)
