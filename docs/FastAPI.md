---
tags:
  - Coding
  - Python
  - API
  - Cheatsheet
---

# FastAPI

_**Author:** Teun Engels_

---

This is a comprehensive cheatsheet of all the basics of FastAPI.

To read more about APIs -> [here](BasicsAPI.md).

## Explanation

The key features are:

- **Fast**: Very high performance, on par with **NodeJS** and **Go**
- **Fast to code**: Increase the speed to develop features by about 200% to 300%.
- **Fewer bugs**: Reduce about 40% of human (developer) induced errors.
- **Intuitive**: Great editor support. Completion everywhere. Less time debugging.
- **Easy**: Designed to be easy to use and learn. Less time reading docs.
- **Short**: Minimize code duplication. Multiple features from each parameter declaration. Fewer bugs.
- **Robust**: Get production-ready code. With automatic interactive documentation.

These key features are from [FastAPI](https://fastapi.tiangolo.com/).

## Installation

### Basic installation

If you are new to installing things for a python project click [here](PyInstalling.md).

First of all you will need fastapi.

```
pip install fastapi
```

You will also need a live server FastAPI recommends uvicorn so we shall use that.

```
pip install "uvicorn[standard]"
```

!!! tip

    You will probably use pydantic in the future so you can already install it.

    ```
    pip install pydantic
    ```

### Running your first API

To run your API you will need a basic `main.py` file. Example:

```py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def get_root():
	return {"response" : "Hello World!!!"}
```

You can now run the command `uvicorn main:app`. The command `uvicorn main:app` refers to:

- `main`: the file `main.py` (the Python "module").
- `app`: the object created inside of `main.py` with the line `app = FastAPI()`.
- `--reload`: make the server restart after code changes. Only use for development.

## Implementation

When building [APIs](BasicsAPI.md#api-basics), you normally use these specific HTTP methods to perform a specific action.

Normally you use:

| Method      | Description                          |
| :---------: | :----------------------------------: |
| `GET`       | :material-check:     Fetch resource  |
| `POST`      | :material-check:     Upload resource |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |


When building an API with FastAPI you will need to make a path operation. This will call a certain function when a operation reaches path x.

???+ example

    This is a **path operation function** example:

    - **path**: is `/`.
    - **operation**: is `get`.
    - **function**: [async](BasicsAPI.md#synchronous-asynchronous) def get_root() 

    ```py
    from fastapi import FastAPI

    app = FastAPI()


    @app.get("/")
    async def get_root():
    return {"response" : "Hello World!!!"}
    ```
    
### Path Parameters

Path parameters are very useful because you can use these parameters directly in the path so that you can target specific items.


???+ example

    This is a **path parameter** example:

    - **path**: is `/items/{item_id}`.
    - **parameter**: is `{item_id}`.
    - **explanation**: now you can target a specific item. You can do this by entering a parameter. 


    ```py
    from fastapi import FastAPI

    app = FastAPI()


    @app.get("/items/{item_id}")
    async def read_item(item_id):
        return {"item_id": item_id}
    ```

    !!! warning

        read_item(item_id) will not validate input. For this you can use a parameter with type.

        ```py
        async def read_item(item_id : int):
        ```

### Request body

When you need to send data from a client to your API, you send it as a request body.

For these models we will use [Pydantic](https://pydantic-docs.helpmanual.io/). View [Installation](#installation) if you need help installing.

Using models will give us a lot of **advantages**

- Read the body of the request as **JSON**.
- **Validate the data**. If the data is invalid, it will return a nice and clear error, indicating exactly where and what was the incorrect data.
- Give you the received data in the **parameter item**.
- Those schemas will be part of the generated schema, and used by the **automatic documentation**.


!!! info

    - A **request body** is data sent by the client to your API
    - A **response body** is the data your API sends to the client.

???+ example

    This is a **request body** example:

    ```py
    from fastapi import FastAPI
    from pydantic import BaseModel


    class Item(BaseModel): # Item will extend the BaseModel Class
    name: str
    description: str | None = None # | None = None will make it an optional parameter
    price: float


    app = FastAPI()


    @app.post("/items/")
    async def create_item(item: Item): # item as instance of Item Model
        return item
    ```

