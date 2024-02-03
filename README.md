# Sonoro (server side)

![Badge en Desarollo](https://img.shields.io/badge/STATUS-COMPLETE-blue)

This is a tiny server only builded for providing static files to the client side of [Sonoro](http://github.com/touzand/sonoro.git). This was build with `Python - FastAPI`

```py
from fastapi import FastAPI
from fastapi.staticfiles import StaticFiles
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI()

origins = ["*"]

app.add_middleware(
    CORSMiddleware,
    allow_origins=origins,
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)

app = FastAPI()
app.mount("/static", StaticFiles(directory="static"), name="static")
```
