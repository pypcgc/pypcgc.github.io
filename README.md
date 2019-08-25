## General

![Logo](static/img/logo.png)

pypcgc alias Python package creater is CLI tool for creating Python packages. It allow you to save information like author name, email, etc and next time you create Python package it can automatically replace these information in `setup.py` and package name. These information is saving to YAML config file located in `~/.pypcgc.yaml`.

##
Install
```
git clone https://github.com/pypcgc/cli-tool.git && cd cli-tool && sudo pip3 install .
```
* Soon on [pypi](pypi.org)!

## Usage

### Saving information to config file
```
>>> pypcgc set --help
Usage: pypcgc set [OPTIONS]

  Set default values to not write them repeatedly

Options:
  -e, --email TEXT             Set default email
  -a, --author TEXT            Set default author name
  -v, --version TEXT           Set default version
  -rp, --requires_python TEXT  Set default python version required
  -l, --project_license TEXT   Set default license
  --help                       Show this message and exit.
```

Example:

This command will save author name to `worepix` and next time you create Python package it will automatically set author name to `worepix` in `setup.py`.
```
pypcgc set -a worepix
```

### Initialization
```
>>> pypcgc init --help
Usage: pypcgc init [OPTIONS]

  Download and initialize pattern

Options:
  -n, --name TEXT              Enter package name  [required]
  -c, --custom TEXT            Custom pattern
  -e, --email TEXT             Email
  -a, --author TEXT            Author name
  -v, --version TEXT           Version
  -rp, --requires_python TEXT  Python version required
  -l, --project_license TEXT   License
  --help                       Show this message and exit.
```
As you can see, argument `--name` is required. This is name of Python package and it is always needed. `Init` command will clone pattern and replace values from shell or from config. If value is in config and also given as argument. Pypcgc will use value from shell.