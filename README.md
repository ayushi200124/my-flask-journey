# How I learned flask <img alt="GIF" src="https://github.com/TheDudeThatCode/TheDudeThatCode/blob/master/Assets/happy.gif" width="30" height="30" />

In this repository I will be decumenting my entire journey of whatever I did during my learning phase in Flask. This is purely written by me for any future references and also to keep a track of important steps. 
To start learning flask we will need to have 
1. VS Code
2. Anaconda 

I will create a seperate conda virtual environment to work in isolated environment inside the python in anaconda
- Activate conda environment `conda activate base`
- Create a new virtual environment `conda create --name demo-flask `
- Get the list of all of them `conda env list`
- Activate the created environment `conda activate demo-flask`
- In case you want to delete the environment `conda env remove --name demo-flask`
- To verify that the environment was removed `conda info --envs`
- To install flask `conda install flask`

Now, I created a new file named **app.py** and write the block of code:
```
from flask import Flask
app = Flask(__name__)
@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"
if __name__=="__main__":
    app.run(debug=True)
```
In the terminal run `python .\app.py` to run flask. To add multiple end-points from our app we add another route function
```
@app.route("/about_me")
def about_me():
    return "<p>Hello,I am Ayushi!</p>"
```
Next we create two folders right in the root directory along side the app.py and name them, **static** and **templates**. Inside templates create a file named **index.html**
We get out emmet boilerplate by writing "!+ emmet abbreviation"

Now we will import render template and direct it to routes for our landing page, our code now looks like:
```
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def hello_world():
    return render_template('index.html')

@app.route("/about_me")
def about_me():
    return "<p>Hello,I am Ayushi!</p>"

if __name__=="__main__":
    app.run(debug=True)
```    
We will add bootstrap to make work easy.
- We go [here](https://getbootstrap.com/docs/5.1/getting-started/introduction/) and copy-paste the starter template into our *index.html* page. Go to *Components* -> *Navbar* -> *Copy-Paste Navbar code into body tag of index.html*
- "Right click+ Format document" for a proper indentation. Go to forms component and copy-paste it into body tag.
- `<div class="container">` alligns the content of container at center according to the display and `<div class="container-fluid">` alligns with the entire screen display (these all are classes of bootstrap. 
- Copy-paste form and table codes respectively and paste under container classes(index.html) and save. 
- `<div class="container my-3">` add space along Y-Axis and `<div class="container mx-3">` add space along X-Axis. Add `<h2>Your To-Do</h2>` under container class. Change the names and neccessary tags in div tag of forms. 
- Time to work with databases. `pip install flask-sqlalchemy` to install sql-alchemy through terminal. 
    - In app.py write `from flask_sqlalchemy import SQLAlchemy`
    - Add minimal code template from [here](https://flask-sqlalchemy.palletsprojects.com/en/2.x/quickstart/)
    - 
