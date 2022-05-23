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
`django-admin strartproject heyapp .
command creates a hey app application project with a simplified folder structure

`django-admin startapp news`
command creates a news app inside heyapp application project

## run your application
`python3.8 manage.py runserver`

# rabbit holes
1. `from django.conf.urls import url, include
ImportError: cannot import name 'url' from 'django.conf.urls`

`from django.urls import include, re_path`

`from myapp.views import home`

`urlpatterns = [`
    `re_path(r'^$', home, name='home'),`
    `re_path(r'^myapp/', include('myapp.urls'),`
`]`



