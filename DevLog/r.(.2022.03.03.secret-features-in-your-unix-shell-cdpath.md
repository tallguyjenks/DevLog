---
id: hdm45inddfpclg3lrovf81x
title: Secret Features in Your Unix Shell Cdpath
desc: ''
updated: 1646356669959
created: 1646356490018
---

## Link

<https://medium.com/@symflower/secret-features-in-your-unix-shell-cdpath-cd0fe29f52cf>

## Notes

> When you pass a relative path to `cd`, then the directories in `$CDPATH` will be used as base directories.

## Example

```bash
mkdir places-to-be
mkdir places-to-be/hogwarts
mkdir places-to-be/narnia
mkdir places-to-be/the-shire
tree places-to-be
# places-to-be/
# ├── hogwarts
# ├── narnia
# └── the-shire

export CDPATH=$CDPATH:$PWD/places-to-be

cd ..
cd ..
pwd
/Users/
cd narnia
~/places-to-be/narnia
pwd
~/places-to-be/narnia

```
