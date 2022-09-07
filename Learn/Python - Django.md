# Python - Django
## Python
Installation [[VM - WSL - SSH - Raspberry#Python]]

### Modules for data manipulation
**NumPy** is a python library for scientific computing containing basic operations such as sorting indexing etc

**SciPy** adds to numpy support to operations like integrations and differentiation

**Matplotlib** is a plotting library for the Python programming language and its numerical mathematics extension NumPy. Matplotlib has pyplot module integrated that allow to make plots like in matlab

**Pandas** is used for data manipulation and analysis. In particular, it offers data structures and operations for manipulating numerical tables and time series

### Modules for ML
**Scikit** is used for machine learing, it's considered a lighter version of tensorflow and it's used for smaller projets

**Tensorflow** is a deep-learning libraly
**Keras** is built on top of Tensorflow is easy to start with

**PyTorch** is a library competing with Tensorflow, it's considered to be an easier alternative to teach and Tensorflow is letely bugged. In 2018 80% of the papers were using Tensorflow it and 20% PyTorch, now it's the oppostite.

### Packet manager
*pip* command is set to only work on venv and `bash -c "pip list"` for global packages

### Virtual environments
Virtual environements are managed either by the already included venv or by _extra/python-virtualenv_

## Django
Django deployment [[Server]]

`django-admin startproject webvalley` to create new project, run it in the projects list directory (will create a folder with all files inside)
-   make migrations to update database
-   if using postgresql
	-   change settings ([docs](https://docs.djangoproject.com/en/dev/ref/settings/))
	-   install _psycopg2_ with pip
	-   import models from database ([docs](https://docs.djangoproject.com/en/2.2/howto/legacy-databases/))

## Django commands
Create app: `startapp weather`
Create super user: `createsuperuser`

Database commands:
- `makemigrations` to create migration files
- `migrate` to update database with migration files

## Linting
Mypy
- [x] Check mypy in vscode

Check out prospector https://github.com/PyCQA/prospector

![Image](https://i.imgur.com/XbgDxUv.png)

