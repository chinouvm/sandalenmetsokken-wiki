---
title: FastAPI
description: The documentation of a basic FastAPI
---

# FastAPI

---

This is a comprehensive cheatsheet of all the basics of FastAPI. Made by [Teun](https://github.com/engelsman16)

  

## Explanation

The key features are:

-   **Fast**: Very high performance, on par with **NodeJS** and **Go** 
-   **Fast to code**: Increase the speed to develop features by about 200% to 300%. 
-   **Fewer bugs**: Reduce about 40% of human (developer) induced errors. 
-   **Intuitive**: Great editor support. Completion everywhere. Less time debugging.
-   **Easy**: Designed to be easy to use and learn. Less time reading docs.
-   **Short**: Minimize code duplication. Multiple features from each parameter declaration. Fewer bugs.
-   **Robust**: Get production-ready code. With automatic interactive documentation.

These key features are from [FastAPI](https://fastapi.tiangolo.com/).


## Installation

### Basic installation 

If you are new to installing things for python project click [here](PyInstalling.md).

First of all you will need fastapi.

````
pip install fastapi
````

You will also need a live server FastAPI recommends uvicorn so we shall use that. 

````
pip install "uvicorn[standard]"
````

### Running your first API

To run your API you will need a basic `main.py` file. Example:

```py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def get_root():
	return {"response" : "Hello World!!!"}
```

You can now run the command `uvicorn main:app`.
The command `uvicorn main:app` refers to:

-   `main`: the file `main.py` (the Python "module").
-   `app`: the object created inside of `main.py` with the line `app = FastAPI()`.
-   `--reload`: make the server restart after code changes. Only use for development.

## Implementation