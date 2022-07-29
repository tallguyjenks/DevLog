

- **Themes**
  - To get a custom theme (_gruvboxdark_) onto my jupyter notebook i used the tool [jupyter-themes](https://github.com/dunovank/jupyter-themes)
  - Then the command i ran was `jt -t gruvboxd -f fira -fs 115`
  - [SO answer about theming notebooks](https://stackoverflow.com/questions/46510192/change-the-theme-in-jupyter-notebook#46561480)
- **Line Magics**
  - Running this in a cell `%lsmagic` will give you a list of magic commands you can run they look like the bash built-ins
  - You can access them like `%ls` `%cp` `%rm` etc. if `Automagic` is turned on then you can run cells with straight up bash in them too. Command flags and everything.
- **Inline Charts**
  - To display an inline chart you need line magic . The one in question is `%matplotlib inline` that will allow you to display charts inline in the notebook
- ==Jupyter Lab==
  - **Installation**
    - pip install jupyterlab
  - **Extensions**
    - pip install jupyterlab-git
    - pip install jupyterlab-pullrequests
    - pip install jupyterlab_github
    - pip install jupyterlab_vim
    - pip install jupyter_contrib_nbextensions
