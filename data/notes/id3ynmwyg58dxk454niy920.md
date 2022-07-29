

- Setup Git Repo and clone
- Make directory and `*.py` file for your project name
  - In that directory add an `__init__.py` file and in that file add code to import your desired objects from your package
  - like "Install module but also add to working session these objects"
- in the root set up a `setup.py` file
  - This file lets the local files be installed by pip as a proper package
- Live iteration through [[s.l.python.tools.jupyter]] lab with magics:

```bash
python -m pip install jupyterlab
python -m jupyter lab
```

```
%load_ext autoreload
%autoreload 2
```

- Upload package to PyPi (Python Package Index)

```bash
python -m pip install twine wheel
```
