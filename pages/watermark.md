---
collapsed:: false
title: watermark
tags: library
---

- used in [[Jupyter]] to grab system and package info:
	- In a jupyter cell:
		-
		  ```python
		  pip install watermark
		  %load_ext watermark
		  %watermark?
		  %watermark --machine --python --packages black,flake8,isort
		  ```
		- something like this should be the output:
			- ![2021_06_18_image.png](https://cdn.logseq.com/%2F07ac90d5-a8a5-495c-84ae-a5c969228e38c1296640-83c9-4588-b41d-f8e91e2ab5822021_06_18_image.png?Expires=4777633268&Signature=aYkwGo-6-yInnOVf0KRs12-YwndjHEQKddn2QYzn2nB8qtenauJEPqRhBix9jXaBrOSRLQa-coLIzweQZi3VCTbve~J65UMjj21DtA7p7lAZ55fgSPEl8ui9JUFOMUlaKwRFukcyqnZBTUzurBGGHXUer-gbgImcZPJ5a8lpH1m-G9jghfeugAZ87cCALsLVP29~behdFc5vKzrS9wdUmit-y9oH~AzjBjRVOTshK3OiQOmrFwCNeKmxfxbCk5S1WYZ5FtcOOzrw-7ulEkbIGlh48JxdwalQUFHGZ~Ar90TVHKEsSdK7qw4kmyuuLe8KLi5XoyxHuRQVuJOnoJhvcQ__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
			-