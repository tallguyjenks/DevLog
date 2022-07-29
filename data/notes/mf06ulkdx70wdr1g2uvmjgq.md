

> Create GUI apps

## Resources

- [Real Python Article](https://realpython.com/qt-designer-python/)
- [Tutorials Point Course](https://www.tutorialspoint.com/pyqt/pyqt_qpixmap_class.htm)
- Using a GUI designer to spit out code for you to use:

```bash
pip install pyqt5 pyqt5-tools pyqt-builder 
```

- open the app builder from [[s.l.powershell]]: `pyqt5-tools.exe designer`
- Quick [[s.l.python.libs.venv]] setup workflow with the designer:

```powershell
pip install venv
python -m venv my_virtual_env
cd my_virtual_env
& scripts\activate.ps1
pip install pyqt5 pyqt5-tools pyqt-builder
pyqt5-tools.exe designer
```
