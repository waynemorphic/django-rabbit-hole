# django-rabbit-hole
Notes on creating a django app and solutions for errors while developing my django application

## installing virtual environment

`sudo apt-get install python3-pip`

`sudo pip3 install virtualenv`

`virtualenv <name of virtual environment>`

## activate the virtual environment
`source <name of virtual environment>/bin/activate`

## install latest django version
`pip install django`

## while in the virtual environment and the application containing folder in your code editor
`django-admin startproject heyapp .`
command creates a hey app application project with a simplified folder structure

`django-admin startapp news`
command creates a news app inside heyapp application project

## run your application
`python3.8 manage.py runserver`

# rabbit holes
1. `ImportError: cannot import name 'url' from 'django.conf.urls`

   solution
    import from django.urls instead
`from django.urls import include, re_path`
    
    ie
`from myapp.views import home`
    include the imported function in the urlpatterns list
`urlpatterns = [`
    `re_path(r'^$', home, name='home'),`
    `re_path(r'^myapp/', include('myapp.urls'),`
`]`

2. `TypeError: __init__() missing 1 required positional argument: 'on_delete'`
This is a testing error in the case of creating models

  solution
in the models file, add the following command in the class with the foreignkey when creating
model relationships
 `on_delete=models.CASCADE`
 
 ie: 
    `editor = models.ForeignKey(Editor, on_delete=models.CASCADE)`
    
3. `It is impossible to add a non-nullable field 'article_image' to article without specifying a default. It is impossible to add a non-nullable field 'article_image' to article without specifying a default`
There is no default provided in the models class for the image column

   solution
   `article_image = models.ImageField(upload_to = 'articles/', default = '')`
   default can either be an empty string or blank can be True
   `
4 `Django DoesNotExist is not defined`
The DoesNotExist class requires a model class to be linked to it so as to query for the existence of data for that class in the database

   solution
   `<Your Model class>.DoesNotExist`



