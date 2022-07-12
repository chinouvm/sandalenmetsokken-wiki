---
tags:
  - Coding
  - Python
  - Setup
  - Cheatsheet
---

# Python Installing

_**Author:** Teun Engels_

---

This document will cover the basics of installing things in python (pip & venv).

## **pip**

Pip is the Python package manager. It’s used to install and update packages. You'll need to make sure you have the latest version op pip installed. For this you can run:

```
py -m pip --version
```

If there is an update available you should run:

```
py -m pip install --upgrade pip
```

## **Virtual Environments**

Virtual Environments allows you to manage separate package installations for different projects. They essentially allow you to create a “virtual” isolated Python installation and install packages into that virtual installation.

When you switch projects, you can simply create a new virtual environment and not have to worry about breaking the packages installed in the other environments.

It is always recommended to use a virtual environment while developing Python applications.

Run this command to create a new venv named `<venv>` .

```
py -m venv <venv>
```
