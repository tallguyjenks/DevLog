

```python
import qrcode
img = qrcode.make('https://www.bryanjenks.dev')
img.save("some_file.png")
```

had to `pip install qrcode`  and also a package dependency `pip install Image`
produced this image, which when scanned goes to the the URL:

![alt](assets/images/Pasted_image_20211103105409.png)
