---
title: Installation Instructions
weight: 1
---

## pip packages installation

To set up this project, you must install flask and the request package.

Follow the [flask python installation instructions](https://flask.palletsprojects.com/en/stable/installation/#python-version) for your specific operating system.

### Windows installation

```powershell
> mkdir myproject
> cd myproject
> py -3 -m venv .venv
# Activate the enviroment
> .venv\Scripts\activate
> pip install -r requirements.txt
```

### Linux/MacOS installation

```shell
$ mkdir myproject   
$ cd myproject
$ python3 -m venv .venv
# Activate the enviroment
$ . .venv/bin/activate
$ pip install -r requirements.txt
```

