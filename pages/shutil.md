---
title: shutil
tags: library
---

-
  > Shell Util
- You can use the function shutil.move() to rename a file:
- import shutil
  shutil.move("server.log", "server.log.backup")
  shutil.move("image.png", "/home/user/")
  shutil.copy() to copy a file:
- shutil.copy("image.png", "/home/user/")
  it contains aliases to the module os and sys and collections:
- >>> import shutil
  >>> shutil.os
  If you want to delete a non-empty directory, use shutil.rmtree() (with cautious).