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


* ### Interactive with the API
*  To run the Interactive python console with the API run the command: _python manage.py shell_
*  ### Some commands in the API:
*   ``` from polls.models import Choice, Question #Import Model ```
*   ``` Question.object.all() ```
*   ``` #Create a question ```
*   ``` from django.utils import timezone ```
*   ``` q = Question(question_text="What's new?", pub_date=timezone.now()) ```
*   ``` q.save() #Save the question ```
*   ``` q.id #Id question ```
*   ``` q.question_text #Acces to field ```
*   ``` q.pub_date #Acces to date ```
*   ``` q.question_text = "What's up?" #Change value of question text ```
*   ``` q.save() = "What's up?" #Update question_text ```
*   At this point include the function __str__() and was_published_recently and is necesary to restart the python shell after the changes
*   ``` #Make sure our __str__() addition worked. ```
*   ``` Question.objects.all() ```
*   ``` #Some keyword arguments ```
*   ``` Question.objects.filter(id=1) ```
*   ``` Question.objects.filter(question_text__startswith='What') ```
*   ``` from django.utils import timezone ```
*   ``` current_year = timezone.now().year ```
*   ``` Question.objects.get(pub_date__year=current_year) ```
*   ``` #Get the data by the primary key ```
*   ``` Question.objects.get(pk=1) ```
*   ``` q = Question.objects.get(pk=1) ```
*   ``` q.was_published_recently() #Make sure our custom method worked ```
*   ``` #To create a choices ```
*   ``` q = Question.objects.get(pk=1) ```
*   ``` q.choice_set.all() ```
*   ``` q.choice_set.create(choice_text='Not much', votes=0) ```
*   ``` q.choice_set.create(choice_text='The sky', votes=0) ```
*   ``` c = q.choice_set.create(choice_text='Just hacking again', votes=0) ```
*   ``` c.question ```
*   ``` #Question objects get access to Choice objects ```
*   ``` q.choice_set.all() ```
*   ``` q.choice_set.count() ```
*   ``` Choice.objects.filter(question__pub_date__year=current_year) ```
*   ``` #Delete one of the choices ```
*   ``` c = q.choice_set.filter(choice_text__startswith='Just hacking') ```
*   ``` c.delete() ```