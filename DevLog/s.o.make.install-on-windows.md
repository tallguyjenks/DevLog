---
id: 0xqxb9yll7zjv0wcpi2zbhs
title: Install on Windows
desc: ''
updated: 1642708476537
created: 1642708465126
---

## Installation on Windows

- Install from [Here](http://gnuwin32.sourceforge.net/packages/make.htm)
- Run `C:\MinGW\bin\mingw-get.exe` to install the Make tools
- Add `C:\MinGW\bin` to your `$PATH`
- make [[s.l.powershell]] alias of `mingw32-make.exe` to `make`

```powershell
New-Alias -Name make -Value mingw32-make.exe
```
