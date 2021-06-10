---
title: pyqt
tags: library
---

- Create GUI apps
- **Resources:**
	- [Real Python Article](https://realpython.com/qt-designer-python/)
	- [Tutorials Point Course](https://www.tutorialspoint.com/pyqt/pyqt_qpixmap_class.htm)
	-
- Using a GUI designer to spit out code for you to use:
	- {{embed ((60be8411-e645-4f47-bcc5-98ede67aeaed)) }}
	-
	  ```bash
	  pip install pyqt5 pyqt5-tools pyqt-builder 
	  ```
	- open the app builder from [[PowerShell]]: `pyqt5-tools.exe designer`
- Quick [[venv]] setup workflow with the designer:
	-
	  ```powershell
	  pip install venv
	  python -m venv my_virtual_env
	  cd my_virtual_env
	  & scripts\activate.ps1
	  pip install pyqt5 pyqt5-tools pyqt-builder
	  pyqt5-tools.exe designer
	  ```