# Django

# Fundations

## 1.1 What is Django and How Web Works

### 1.1.1 Django

#### Django Features

* Batteries Included Framework

  * Admin Site
  * ORM
  * Authentication
  * Caching

### 1.1.2 How the Web Works

#### Web Concepts

* website application

  * Front-End

    Client Machine
  * Back-End

    Web Server
  * URL

    Uniform Resource Locator
  * HTTP

    Hypertext Transfer Protocol

    request response protocol

    send  request and return response

#### Server&Client Workflow

* server-side tools

  * DJANGO

    python
  * ASP.NET CORE

    C
  * EXPRESS

    javascript

* client-side tools

  * REACT
  * ANGULAR
  * VUE

1. html document
2. data only and make client generate the html
3. the server is the gateway to data

    * endpoint
    * interface/api

      all the endpoints consist interface/api with which the client can interact with the server

## 1.2 Buidling Django Project

(based on editor VS code)

(give a structure tree of Django Project here to map to)

* ​`**project folder**`​

  * ​`**urls.py**`​

    ```python
    #to route to application and url configuration already exist
    from django.contrib import admin
    from django.urls import path, include
    urlpatterns = [
        path('admin/', admin.site.urls),
        path('application/', include('application.urls'))
    ]
    #line 6 means for urls of the project with 'application/' in them -> refer to 'application.urls'
    ```

  * ​`**application folder**`​

    in app folder migrations folder is for generating database tables

    * ​`**urls.py**`​

      mapping urls to views

      every app can have a own configuration

      also can add this one in app folder to the main project

      ```python
      from django.urls import path
      from . import views
      #dot is the current folder

      #URLConf Module
      #in VS Code put curser on path() can see infomation of the function
      urlpatterns=[
      	path('application/say_hello_function/', views.say_hello_function)
      ]
      #'application/say_hello_function' -> a url/route type is string
      #views.say_hello -> views function
      #call the function -> views.say_hello()
      #reference the function -> views.say_hello
      #if in urls.py application url has been mapped 'application/' in line 8 can be omited
      #always end the routes with forward slash
      ```
    * `**models.py**`

      monetary -> decimal field

    * ​`**views.py**`​

      view is the function take request and return response

      request handler (http)

      action request -> response

      view in django doesn't equal to <u>normally said view!!!(is called template in django)</u>

      view function should map to a url -> get a request from the url -> view.py be called

      map urls to view functions

      ```python
      #1st way to give a response
      from django.shortcut import render
      #render -> template -> html makeup -> client

      #2nd way to give a response
      from django.http import HttpResponse
      #request->object? HttpRespense->function

      #1st
      def say_hello_function(request):
      	return render(request, 'say_hello.html',{'name':'Charton'})

      #2nd
      def say_hello_function(request):
      		#pull data from db
      		#transform
      		#send email
      	return HttpResponse('Hello World')
      ```

    * ​**`templates`**​

      use template to return html content to the client

      * ​`say_hello.html`​

        ```html
        {% if name %}
        <h1>Hello {{ name }}</h1>
        {% else if %}
        <h1>Hello World</h1>
        {% endif %}
        ```

‍

### 1.2.0 Environment

#### Set Environment

(need to be done)

‍

#### Create Django Project

​`django-admin`​and `python manage.py`​ have the same commands

use the python installed in the env (not the global one)

```shell
django-admin startproject project_name_here . 
##dot means django will use `project_name_here` as the directory (no more additional one)

python manage.py runserver
##'python manage.py' is the wrapper for django-admin to know the setting of project

python manage.py runserver 9000 
##if don't add default port is 8000
```

‍

### 1.2.1 Data Model

#### Create Application

* project is a group of apps (with different function)
* go to `setting.py`​ can see installed apps

```shell
python manage.py startapp application_name_here
```

‍

#### Build a Data Model

* relationship

  * one-to-one
  * one-to-many
  * many-to-many

* association class

  1. relationship with an association class
  2. 2 one-to-many relationships

‍

#### Organize Models in Application

1. all the models in one app

    Monolith

    Unix Philosophy
2. how to seperate models in different app?

    independency and subsequently orders

    1. seperate piece of functionality
    2. each app is self-contained and provide a specific piece of functionality
    3. zero coupling

‍

### 1.2.2 Database

‍

### 1.2.3 Django ORM

‍

### 1.2.4 Admin Site

‍

# Advanced

## 2.1 RESTful APIs and Django REST Framework

* API

  Application Programming Interface

  Client <-APIs-> <-End Points <- Server
* REST

  Representational State Transfer

  a bunch of rules

  * RESTful API

    which confirms to these rules
  * 3 important concepts

    1. Resources
    2. Representations
    3. HTTP Methods

### 2.1.1 Resources, Representations and HTTP Methods

#### Resources

* Client use URL to reach Resources (like objects of an application)

  http://website.com/resource1/id/resource2/id/...

  resources can contain other resouces

‍

#### Representations

use URL to identify a resource

* resources on client

  server return resources to client in formats/representations

  1. HTML
  2. XML
  3. JSON
* resources on server

  1. objects
  2. instances of Python classes

##### JSON

* JavaScript Object Notation

  * key value pairs/properties

    key --> strings

    value --> anything

```javascript
#how javascript present data
{
	"name": "Charton",
	"age": 23,
	"is_online": true,
	"employer": {},
	"interests": []
}
```

##### XML

##### HTML

#### HTTP Methods

* end points can allow multiple operations (read only or modify data)

  client --> HTTP methods --> server

  what it wants to do with the resources

  * GET
  * POST
  * PUT
  * PATCH
  * DELETE

‍

### 2.1.2 Building REST APIs in Django

#### Install Django REST Framework

​`pip install djangorestframework`​​​

​`#INSTALLED_APPS`​​​ add "rest_framework"

‍

#### Create API views

python interpreter should be the one in the env

‍

#### Serializer

convert a model instance to dictionary

python class instance/object -> serializer -> python dictionary ->JSON

‍

lookup parameter?

‍

#### Django-Filter: Filter, Sort and Search

​`pip install django-filter`​

https://q1mi.github.io/Django-REST-framework-documentation/api-guide/filtering_zh/

https://www.django.cn/article/show-37.html

‍

## 2.2 Advanced API Concepts

‍

## 2.3

‍

## 2.4

‍

## 2.5

‍
