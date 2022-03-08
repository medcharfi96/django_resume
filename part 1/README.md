# Part 1

This part include 
- install Django
- create first project
- path, views, template
- static files

## First course : Install env
create virtuel environoment
``` 
python -m venv .[name of virtual  env]
```
activate venv
```
source ./[name of virtual  env]/bin/activate
```
install django in venv
```
pip install django
```
install all requirements
```
pip install -r [Filename].txt
```
Make requirement file
```
pip freeze > [name of file].txt
```
## Second course :  start your first project
create the project
```
django admin startproject
```
runserver
```
python manage.py runserver
```

- the server is designated for the dev not for the production
for security measures

## third course :  start your first path/url

- for solving the probleme to access to  admin main page  you must migrate
```
python manage.py magrate
```
type of path in urls.py
```
path('name of page', page_path)
```
Add path  for first page
```
path('', page_path)
```
Distribution of URLs
```
https://docs.djangoproject.com/fr/3.1/topics/http/urls/#url-dispatcher
``` 
Creation of a template
```
Add templates folder
Create HTML file
Change the view using function render
Add  request  and HTML page name  
```
```
from django.shortcuts import render

def index(request):
    return render(request, "index.html")
```
## fourth course :  start your application

Create  application
```
python manage.py stratapp
```
- create as package not a diractory

Add app name
```
Add name application in Unstalled_APP in the main settings.py
```
including new app url 
```
For best  practise:
- make new file urls.py  in new app diractory
- add the new url in  the file urls.py of the app
- make the new view in the dirc file view.py
-add the new file urls.py of the new app  in the  main urls.py file of the hole  app

```
** this way  help  to  distingue new app and do not have trublle in the project
**  this way  help to  reuse app  for many project

- Django architecture
```
application -> main application folder.

migrations -> folder that contains the model migration files.

__init__.py

admin.py -> file to save templates in the admin interface.

apps.py -> file to define application configurations

models.py -> file in which the application models are created.

test.py -> file to create the unit tests of the application

views.py -> file to create the views of the application.
```