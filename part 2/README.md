# Part 2

This part include 
- Models
- Request
- Model relation
- Vues
- Django template language

## First course: Model
Build model
```
python manage.py startapp (app name)
Add app in installed_APPS in file settings.py ;) 
from  django.db import models 
Start creating model
```
as an exemple
```
from django.db import models

class Article(models.Model):
```
__each model had an id field automatically__
- here some option using filed:
  - blank  =  true  => field can be empty ||fields not required
  - blank  = false  => field can't be empty || champs  required
  - null = true  => get automatically NULL value if it's empty

>it is not advisable to put null in the charFiled but it is advisable to put it in the fields of INtegerField and FloatFiled
>for DATEField type variables must set null to True if you do not want to pass a data

Create Migration
```
python manage.py makemigrations
```
Applicate migration
```
python manage.py migrate
```

any migration creates a file by the name of the change done in Model.

shows the migrations as sql code
```
pyhton manage.py sqlmigrate (nom de  APP) (nom de fichier de migration)
```
## Second course: Request

open shell project
```
python manage.py shell
```

Create object from shell
```
create an  instance 
(instance_name).save()
```
or without save like:
```
(Class_name).object.create()
```

Get all obect
```
name_class.objects.all()
```
You can retrieve a specific instance with the get method:
```
name_class.objects.get(attribut= value)
```

>if we want to recover by primary key we use pk

Delete all  object
```
name_class.objects.all().delete()
```
delete one object
```
   var =  class_Name.objects.all()
   var[index].delete()
```

filter using field
```
Article.objects.filter(title="the desired title")
```
__Some tips__
>instance is a DB row record

>the model represents the table in comics

>the class attributes represent the columns

## Third course: Model relation

Create superuser
```
python manage.py createsuperuser
```

__relation many To 1__ 
```
Add a foreign key choosing option on delete
```
**Options**
1. CASACADE (if the 1 is dead Many dead)
2. SET_DEFAULT(set  default value if 1 Dead)
3. SET_NULL(Set null Value if 1 DEAD)
4. PROTECT (Can not be DEAD)

relatio Many To Many
```
models.ManyToManyField(nom_class to reffer)
```
>This type of relation allows to create a new table which contains the 2 primary keys of the tables

>To remove a relation to an object, use the remove command.

>To remove all relations to an object, use clear

>Add : Add relation

>Set : specify one or more relations and overwrite the old ones




