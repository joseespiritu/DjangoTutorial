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
* ### Create a Model:
*  Each model is represent by a Class in the file _mysite/models.py_, it contains the columns represent as variable names
*  To instance an App, change the file _mysite/setting.py_ in the sectiton INSTALLED_APPS, add the lines _'polls.apps.PollsConfig'_
*  To make the changes on Database with the new models and App run the command: _python manage.py makemigrations polls_
*  If you want to see the SQL querys, run the command: _python manage.py sqlmigrate polls 0001_
*  To check if exist any problem on your models or migrations, run the command: _python manage.py check_
*  Finally to update Database run the command: _python manage.py migrate_