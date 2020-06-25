# DjangoTutorial
Django Tutorial Full Course From Documentation
## Initial Configuration
* ### Create a Virtual Enviroment _(venv)_ by console, with the next command lines in a folder:
*  Create venv: _python -m venv djangotutorial_
*  Run venv: _djangotutorial\Scripts\activate.bat_
* ### Install Django in our venv, with the next command lines (to follow this step you need to activate venv):
*  pip install Django==3.0.7
*  Prefer to create file _requirements.txt_ (contains all the version that used in this project)
*  If you got file _requirements.txt_ then you need to execute the next command line: _pip install -r requirements.txt
* ### Create a project:
*  Command Line: _django-admin startproject mysite_ in the path our venv
* ### Create an App in our project:
*  To create your app, make sure you’re in the same directory as manage.py and type this command: _python manage.py startapp polls_
* ### Create Database:
*  In this project we use SQLite3, into _mysite/settings.py_ check the parameters by default set with SQLite 3, not is necesary NAME, HOST, PASSWORD
*  Run the command: _python manage.py migrate_ to create Database
