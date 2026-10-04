# bg-remover-fullstack-app
The webapp is for image processing which removes a background from an image.

## Prerequisites
You should be comfortable with:

Basic HTML: You know what inputs, buttons, images, and divs do.

Basic CSS: You can style a page and make it look presentable.

Basic JavaScript: You know how to listen for a button click and send a request using fetch.

Make sure you have these installed:

Python 3.9 or newer

Git

A code editor like VS Code

A browser
Project Structure
Create a new folder called:

background-remover
Inside it, create a folder for the backend:

background-remover/
  backend/
Move into the backend folder:

cd background-remover/backend
Now create a virtual environment:
```
python -m venv env
```
A virtual environment keeps this project’s dependencies separate from everything else on your computer. This is standard practice and something you’ll see in real projects.

Now activate it:

macOS or Linux:
```
source env/bin/activate
```
Windows:

env\Scripts\activate
Now create a folder for your application code:

mkdir api
Your structure should now look like this:
``
background-remover/
  backend/
    env/
    api/
```
At this stage, nothing looks impressive yet. That’s normal.

Installing FastAPI
We’ll use FastAPI to build the backend API.

Install it together with Uvicorn, which is the server that runs our app:
```
pip install fastapi uvicorn
pip install python-multipart

```
FastAPI allows us to define endpoints clearly and with very little code, which is perfect for us.

Creating the First Backend File
Inside the api folder, create a file called main.py.

Add the following code:
```
from fastapi import FastAPI

app = FastAPI()

@app.get("/health")
def health():
    return {"status": "ok"}
```
Let’s pause and understand what this does.

We created a FastAPI application

We added a /health endpoint

This endpoint simply returns a message

## Running the Server
From inside the backend folder, start the server:

uvicorn api.main:app --reload
Now open a new terminal and run:

curl http://localhost:8000/health
You should see:

{"status":"ok"}
