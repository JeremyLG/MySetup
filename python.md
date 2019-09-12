# Python Tips

## Create and setup env for Atom

```bash
python3 -m venv venv
source venv/bin/activate
pip3 install ipykernel
python3 -m ipykernel install --user --name venv
```

## Setup Atom IDE for Python

### Packages

- **Hydrogen** : Links Atom with Jupyter kernels, useful to execute code in an interactive manner
- **ide-python** : global package with *linting*, *code style checking*, *code formatting*, *errors* and
*completions* features
- **python-indent** : Allows to automatically indent code when you line breaks
- **atom-mypy** : Allows *type checking* via the *typing* package in Python **3.6**
- **python-docstring** : Adds a docstring with the shortcut *ctrl+alt+d*

#### Other useful packages

- **better-git-blame** : Allows you to check history on files with *ctrl* + *b* shortcut
- **highlight-selected** : Highlights in files all occurences of the word that is selected
- **platformio-ide-terminal** : Add a super terminal in the atom IDE
- **copy-filename** : Allows you to right click a file and copy its filename easily (useful with DBT)
- **git-control** : Excellent UI Git interface to fetch remote branches and do many more things

### More details on some packages

#### ide-python

- You should first install **pyls** package :
```python
pip install "python-language-server[all]" --upgrade
```
- Disable *PyDocStyle*, so you don't get unnecessary docstyle warnings
- Set *Max Line Length* at 99 instead of 79 in *PyCodeStyle*. You should also modify global parameters
of Atom Editor and set *Preferred Line Length* to 100

#### my-py

- Warning : it exists multiple my-py package, I personally use **atom-mypy** in version
**0.2.4** with around 320 downloads on Atom.
- You should add *--ignore-missing-imports* in my-py options, this is located in the mypy Atom package options with the field **mypy command** :
```python
python -m mypy --ignore-missing-imports
```

## Export Python project to offline production

#### Local commands to export project for production
```python
pip freeze > requirements.txt
pip download -r requirements.txt -d pypi
```

#### Production commands to deply the project offline
```python
conda create -n venv OU python -m venv venv
venv/Scripts/activate
pip install --no-index --find-links pypi/ -r requirements.txt
```

## Python Wheel to distribute packages in PySpark
```bash
source activate venv
tar -xvf python_package_to_ditribute.tar.gz
cd python_package_to_ditribute
python setup bdist_wheel
cd dist
unzip python_package_to_distribute-***.whl
hdfs dfs -put /user/tricky/venv
```

Possibility to do it with **.egg** format instead of **.whl**
