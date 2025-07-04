# Chapter 0: Django:   // Under-development

## Basic Django Terminology

### What is Django?

* Django is a high-level Python web framework that helps build secure, scalable websites quickly.
* It follows the "batteries-included" philosophy, meaning it includes many built-in features by default.
* Django is used to build everything from simple websites to complex web applications.
- Django is a high-level Python web framework that enables rapid development of secure and maintainable websites.

 - It encourages clean, pragmatic design and follows the "Don't Repeat Yourself" (DRY) principle.

 - 2003: Created by developers at the Lawrence Journal-World newspaper to manage news content.
  
 - 2005: Open-sourced and named after jazz guitarist Django Reinhardt.
  
 - Now maintained by the Django Software Foundation, it is one of the most popular web frameworks for Python.


### What is a Web Framework?

* A web framework is a set of tools that makes it easier to build websites and web apps.
* It helps manage common tasks like URL routing, form handling, databases, and user authentication.
* Django is one such framework that uses Python as the programming language.

---

## Django Project

* A Django project is the main folder that contains your website’s full configuration.
* It includes files like `settings.py`, `urls.py`, `wsgi.py`, and `asgi.py`.
* A single project can contain many apps that work together to create one site.
* The project defines global settings and acts as the central controller of the application.

---

## Django App

* An app is a component of a project that performs a specific function (like a blog or login system).
* Apps help in organizing code into smaller, manageable parts.
* Multiple apps can be used inside one project.
* Each app includes its own views, models, templates, and URL configurations.

---

## MVT Pattern (Model–View–Template)

* Django follows the MVT architectural pattern to separate concerns in code.
* The Model handles data and database operations.
* The View processes requests and returns responses.
* The Template handles how data is displayed in HTML to the user.

---

## Models

* Models define the structure of the data in the database using Python classes.
* Each model class corresponds to a table in the database.
* Django’s ORM uses these models to automatically create and manage database tables.
* Fields in a model represent columns in the table (like text or date).

---

## Views

* Views process user requests and return appropriate responses.
* They are the connection between the models (data) and templates (UI).
* Views can be written as functions or classes.
* They determine what data is shown and how the user interacts with it.

---

## Templates

* Templates are HTML files used to display data to the user.
* They use Django’s templating syntax to include dynamic data in HTML.
* Templates keep the presentation logic separate from business logic.
* Template tags and filters are used to handle conditions and loops.

---

## URLs and URL Dispatcher

* The URL dispatcher maps browser requests (URLs) to views in Django.
* Defined in `urls.py`, each path is connected to a view function or class.
* `include()` is used to organize app-level URLs.
* It allows for clean and maintainable routing logic.

---

## Django ORM 

* ORM stands for Object-Relational Mapping.
* It allows you to interact with the database using simple Python code instead of writing SQL manually.
* You can create, read, update, and delete data by calling Python methods.
* The ORM connects your Django models to actual database records.
* It makes database work easier and less error-prone for beginners.

---

## Migrations

* Migrations are files Django creates to apply changes in models to the actual database.
* Use `makemigrations` to create migration files and `migrate` to apply them.
* They track and apply changes like new fields or tables.
* Migrations help keep your database and code in sync.

---

## Forms

* Forms in Django collect and validate user input.
* `Form` handles custom fields, while `ModelForm` connects directly to a model.
* Django forms help prevent invalid or malicious data from being submitted.
* They support clean data validation and user-friendly error handling.

---

## Admin Interface

* Django provides a built-in admin panel to manage data models through a browser.
* It allows developers and site owners to add, edit, or delete data quickly.
* Models must be registered to appear in the admin.
* The admin panel is customizable and useful for non-developers too.

---

## Authentication

* Django includes built-in tools for user login, logout, and password management.
* It supports sessions, groups, and permissions for controlling access.
* The default `User` model can be customized or replaced.
* Authentication is secure by default and works out of the box.

---

## Static Files and Media

* Static files are CSS, JavaScript, and images used in the frontend.
* Media files are user-uploaded files like photos and documents.
* Django uses separate folders and URLs for static and media files.
* You must configure `STATIC_URL` and `MEDIA_URL` in your settings.

---

## Middleware

* Middleware is a set of functions that run before or after each request or response.
* They perform common tasks like authentication, security, and session handling.
* Middleware is defined in the `MIDDLEWARE` setting as a list.
* They can be custom-written or use Django’s built-in options.

---

## Django Shell

* The Django shell is a command-line tool to test and run Django code interactively.
* Run it using `python manage.py shell`.
* It loads all models and project settings automatically.
* Great for testing queries and understanding how models work.

---


# Django Built-in Features

## 1. Admin Interface

* Django includes a built-in admin panel to manage database models.
* It is auto-generated from models you define and is ready to use after login.
* Site admins can add, edit, and delete data without touching code.
* You register models using `admin.py` to make them available in the admin.

---

## 2. Authentication System

* Django has a complete authentication system with login, logout, and password handling.
* It provides secure session management and password hashing.
* User permissions and group-based access control are built in.
* You can customize the User model or extend it to add new fields.

---

## 3. ORM (Object-Relational Mapper)

* Django’s ORM lets you use Python code to work with databases instead of SQL.
* You can create, read, update, and delete records using model methods.
* It keeps your Python code and the database tightly linked.
* ORM makes working with databases safer and easier to understand.

---

## 4. URL Routing System

* Django routes incoming web requests (URLs) to specific views using `urls.py`.
* It uses `path()` and `re_path()` for clean and readable URL mapping.
* Apps can have their own `urls.py` and be included in the main project.
* This separation keeps your app modular and maintainable.

---

## 5. Templating Engine

* Django’s template engine lets you build dynamic HTML pages.
* It separates the presentation layer from Python logic.
* You use template tags and filters to display data, loop through content, or apply logic.
* Templates are stored in a `templates` folder within the app or project.

---

## 6. Middleware Support

* Middleware are small programs that run between the request and response cycles.
* They can handle tasks like security, sessions, or content modification.
* Django includes useful middleware by default, like CSRF protection and user auth.
* You can write your own middleware or remove/replace the defaults.

---

## 7. Forms and ModelForms

* Django includes a robust system to handle forms and user input.
* Forms handle validation and rendering HTML inputs easily.
* `ModelForm` connects a form directly to a database model.
* This reduces repetition and ensures clean data storage.

---

## 8. Sessions

* Django can store user session data across requests.
* It supports server-side sessions using the database or file storage.
* Sessions help maintain user state like login info or shopping carts.
* All of this works without exposing sensitive data to the browser.

---

## 9. Messages Framework

* Django allows temporary messages (e.g. “Post created successfully”) to be stored and shown to users.
* These messages are stored during one request and displayed on the next page.
* You can assign message levels like info, success, warning, or error.
* Messages improve the user experience and communication.

---

## 10. Static Files Handling

* Django supports serving static files like CSS, JS, and images during development.
* You define a `STATIC_URL` and collect all static files in one directory.
* In production, static files are served via a dedicated server (e.g., NGINX).
* The `collectstatic` command prepares files for deployment.

---

## 11. CSRF Protection

* Django provides built-in protection against Cross Site Request Forgery attacks.
* It adds a CSRF token to all forms and checks it before processing requests.
* This ensures form data is submitted by legitimate users.
* You can use `{% csrf_token %}` in templates to enable protection.

---

## 12. Internationalization (i18n)

* Django supports translation and formatting for multiple languages and locales.
* It helps build applications that can serve users around the world.
* You can mark text for translation and use different locale settings.
* Built-in tools help manage translation files and language switching.

---

## 13. Error Handling and Debugging Tools

* Django shows detailed error pages in development with stack traces and hints.
* You can customize 404, 500, and other error pages.
* Settings like `DEBUG=True` help while building, and should be `False` in production.
* It’s designed to help you catch and fix bugs quickly and clearly.

---




# Chapter 1: Initial Set Up of Django   


 
 - This chapter covers how to properly configure your computer to work on Django projects.
 
 - We start with an overview of the command line and how to install the latest version of Django and Python.
 
 - Then we discuss virtual environments, git, and working with a text editor.
 
 - By the end of this chapter you’ll be ready to create and modify new Django projects in just a few keystrokes.

 - Before we explore about Django we need to know about some general inforamation,
---
 # Command line in django

**Using the Command Line:**

- The command line is essential for Django development, used for setting up and managing projects.

**To Open the Command Line follow these steps,**
 
 
Mac: Open Terminal from

Applications > Utilities > Terminal


Windows: Open Terminal using

Use PowerShell (recommended over Command Prompt) or use git bash 

**Note: vs code has default terminal build-in connected with powershell**

![image](https://github.com/user-attachments/assets/8d72b467-d777-49ba-b07e-00f2e064bde1)

---

| Command      | Description                 |
| ------------ | --------------------------- |
| `cd`         | Navigate into a directory   |
| `cd ..`      | Move up one directory       |
| `ls` / `dir` | List files (Mac / Windows)  |
| `pwd`        | Show current directory path |
| `mkdir`      | Create a new directory      |
| `touch`      | Create a new file on mac      |


---

# How to install django:

**Installing Python**

Python is required for Django development.

Follow the steps below to install it on your system.

---

**For macOS**
Check if Python is installed:

terminal
```
python3 --version
```

If not installed, use Homebrew:

terminal
```
brew install python
```
---
**For Windows,**

Download Python from the official site:

https://www.python.org/downloads/windows/

Run the installer:

Make sure to check the box that says "Add Python to PATH"

Note:If the python isn't working check out this website for guide,https://realpython.com/installing-python/

---

**For Linux**

Use your package manager. Example for Debian/Ubuntu:

terminal
```
sudo apt update  
sudo apt install python3 python3-pip
```

Verify Installation
Run the following in your terminal or PowerShell:

terminal
```
python3 --version
pip3 --version
```
If you see version numbers, Python and pip are successfully installed.

---


# installation of django

 
**1. Make sure Python is already installed in our system for django**
 terminal
```
python --version 
 ```
---
**3. Install django by using pip**

**Command:**
terminal
``` 
pip install django 
```

The temrinal will show you the following in proccces of insatllation,

![image](https://github.com/user-attachments/assets/3edeb66f-d541-4cf8-b973-2646262fd218)

---

**3. To check django version:** 
 terminal
 ```
py -m django --version
```

---

# Virutual environment

**Using Virtual Environments**

Virtual environments are isolated containers that hold the dependencies for a specific Python project.

This prevents conflicts between projects using different package versions 

---

**Why Use Virtual Environments?**

- Keeps project dependencies separate

- Avoids version conflicts

- Ensures consistent environments across systems

- Standard practice in Python development

---

**Note:**

- In python we have a  built-in Python module used to create isolated virtual environments

- we also have a  third-party tool called pipenv that combines virtual environment management and package management into a single workflow.


---

**Example Workflows**

| Platform    | Create Environment      | Activate Environment        |
| ----------- | ----------------------- | --------------------------- |
| Windows     | `python -m venv .venv`  | `.venv\Scripts\activate`    |
| macOS/Linux | `python3 -m venv .venv` | `source .venv/bin/activate` |

---

**basic of venv:**

terminal

- python -m venv .venv            # Create environment
- .venv\Scripts\activate          # Activate on Windows
- source .venv/bin/activate       # Activate on macOS/Linux
- pip install django              # Manually install packages
- pip freeze > requirements.txt   # Save dependencies



---


# Installation of GIT


### What is Git?

**Git** is a **version control system** used to track changes in code, collaborate with other developers, and revert to earlier versions of a project when needed.

It works similarly to “track changes” in Microsoft Word or Google Docs, but is built specifically for software development.

* [Official Git Website](https://git-scm.com/)
* [What is Version Control? (Wikipedia)](https://en.wikipedia.org/wiki/Version_control)

---

### Install Git

#### On macOS

**Terminal:**

```terminal
brew install git
```

**Why:**
This command uses **Homebrew**, a macOS package manager, to download and install Git. It’s the recommended way for Mac users.

---

#### On Windows

1. Visit [Git for Windows](https://gitforwindows.org/)
2. Click the **Download** button
3. Follow the installation prompts

**Why:**
This provides Git along with Git Bash (a command-line tool), which allows you to use Git commands on Windows easily.

---

### Configure Git (One-Time Setup)

After installation, you need to tell Git your name and email address. This information will be attached to your commits.

**Terminal:**

```terminal
git config --global user.name "Your Name"
git config --global user.email "yourname@email.com"
```

**Why:**
Git uses this information to record who made each change. You can update it anytime using the same commands.

---

### Verify the Installation

**Terminal:**

```terminal
git --version
```

**Why:**
This checks if Git is correctly installed and displays the version number.

---

### Common Use Cases for Git

* Initialize and manage local repositories
* Commit and track file changes
* Collaborate via GitHub, GitLab, etc.
* Safely branch and merge features or fixes

---

### Text Editors
 
The final step is our text editor. While the command line is where we execute commands for our programs, a text editor is where the actual code is written. 
 
The computer doesn’t care what text editor you use–the end result is just code–but a good text editor can provide helpful hints and catch typos for you.
 
 Experienced developers often prefer using either Vim27 or Emacs28, both decades-old, text-only
 editors with loyal followings.
 
 However each has a steep learning curve and requires memorizing many different keystroke combinations. I don’t recommend them for newcomers 

 
 Modern text editors combine the same powerful features with an appealing visual interface.
 
 My current favorite is Visual Studio Code29 which is free, easy to install, and enjoys widespread
 popularity.
 
 If you’re not already using a text editor, download and install Visual Studio Code30
 now.
 
---

# Chapter2: Hello World App

 - In this chapter we’ll build a Django project that simply says “Hello, World” on the homepage.
   
 - This is the traditional way to start a new programming language or framework.

### Here step by step through **Chapter 2: Hello World App** for a Django project, covering:

1. Initial Setup
2. Create an App
3. URLs, Views, Models, Templates
4. Hello, World!
5. Git
6. Optional: GitHub and  SSH Key

I'll also give you a **structure** you can create manually, along with code and commands.

---

### Structure


![image](https://github.com/user-attachments/assets/4c1cac06-3d7c-4c4a-80d7-20126d2e5756)




###  1. Initial Setup

####  Install Django (if not already)

bash

```
pip install django
```

####  Start a Project

bash

```
django-admin startproject helloworld_project
cd helloworld_project
```

---

###  2. Create an App

bash

```
python manage.py startapp core
```

This creates a new Django app named `core`.

**Register the app in `settings.py`:**

python

```
# helloworld_project/settings.py
INSTALLED_APPS = [
    ...
    'core',
]
```

![image](https://github.com/user-attachments/assets/f8b56652-9022-4b1a-a531-6f96c3398e41)


---

### 3. URLs, Views, Models, Templates

#### Project-level URL setup:

python

```
# helloworld_project/urls.py
from django.contrib import admin
from django.urls import path path, include  #path:Lets you define URL patterns ,include: Lets you import URL patterns from another file

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('core.urls')),  # Link to app URLs
]
```

#### App-level URL setup:

Create `core/urls.py`:

python

```
# core/urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.hello_world, name='hello_world'),
]
```

#### Views:

python

```
# core/views.py
from django.http import HttpResponse

def hello_world(request):
    return HttpResponse("Hello, World!")
```

---

### 4. Hello, World!

Run the development server:

bash

```
python manage.py runserver
```

Visit [http://127.0.0.1:8000/](http://127.0.0.1:8000/) — you’ll see "Hello, World!"

![image](https://github.com/user-attachments/assets/286a0af8-41f1-4510-829c-b2d297951544)


---



### 5. Git

#### Initialize Git:

bash
```
git init
```

#### Create `.gitignore`:
- If you don't have a gitignore file ,then create it in your project root folder (e.g., HelloApp_Django), create a new file named: .gitignore

-  We can use this command in Powershell ,

```
  New-Item -Name ".gitignore" -ItemType "File"

```




bash
```
__pycache__/
*.pyc
db.sqlite3
.env
```



#### Add and Commit:

bash

```
git add .
git commit -m "Initial Hello World Django app"
```




---

###  Optional: 6. GitHub

#### Create a repo on [GitHub](https://github.com/new)

#### Link it:

bash

```

git remote add origin git@github.com:yourusername/helloworld-django.git
git push -u origin main
```

---





# Chapter 2: Pages App

- In this chapter we will build, test, and deploy a Pages app with a homepage and about page.
  
-  We’ll learn about Django’s class-based views and templates which are the building blocks for the more complex web applications built later on in the book.


Here’s a GitHub-friendly, chapter-style breakdown and explanation for building a **Django Pages App** with homepage and about page using class-based views and templates:

---

 Here's a **concise algorithm-style breakdown** of the Django Pages App project setup using class-based views and templates:


### **Algorithm: Build a Django Pages App**

1. **Start Project Setup**

   * Install Django using `pip`.
   * Create a Django project: `django-admin startproject pages_project`.

2. **Create Pages App**

   * Inside the project directory, run: `python manage.py startapp pages`.
   * Add `'pages'` to `INSTALLED_APPS` in `settings.py`.

3. **Configure URLs**

   * Create `pages/urls.py` with paths for homepage and about page.
   * Include `pages.urls` in the project's main `urls.py`.

4. **Create Views**

   * Use `TemplateView` to define `HomePageView` and `AboutPageView` in `views.py`.

5. **Create Templates**

   * Inside `pages/templates/`, create `home.html` and `about.html` with simple HTML headings.

6. **Run the App**

   * Run `python manage.py runserver`.
   * Visit `http://127.0.0.1:8000/` for homepage and `/about/` for the about page.

7. **Initialize Git**

   * Run `git init`.
   * Create `.gitignore` to exclude files like `__pycache__/`, `*.pyc`, `db.sqlite3`, `.env`.
   * Commit initial setup with `git add .` and `git commit -m "Initial commit"`.

8. **(Optional)Push to GitHub**

   * Create a GitHub repository.
   * Add remote, rename default branch to `main`, and push code.

  
---

# Here is a step by step guide:

### 1. Initial Set Up

**Install Django**

bash

```
pip install django
```

### Check django version

bash

```
python -m django --version 

```

**Create a Django Project**

bash

```
django-admin startproject pages_project         #creates the project folder
cd pages_project                                 #directs to the folder
```

---

### 2. Create An App

**Create a new app called `pages`**

bash

```
python manage.py startapp pages                    #craetes an app inside project called page
```

**Add `'pages'` to `INSTALLED_APPS` in `pages_project/settings.py`**

python
```
INSTALLED_APPS = [
    ...
    'pages',                     #this important,if not give app will not be overlooked by compiler
]
```

![image](https://github.com/user-attachments/assets/1af94c0c-6e87-461b-9f36-20cfc999ef63)


---

### 3. URLs, Views, Models, Templates

**Create URL configurations**

In `pages/urls.py` (create this file):

python

```
from django.urls import path
from .views import HomePageView, AboutPageView

urlpatterns = [
    path('', HomePageView.as_view(), name='home'),                                  #url for homepage
    path('about/', AboutPageView.as_view(), name='about'),                          #url for aboutpage
]
```

In `pages_project/urls.py`:

python

```
from django.contrib import admin
from django.urls import path, include                           #this is important or complier will not know about the include function

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('pages.urls')),                               #this will include the page url in pages_project's urls
]
```

---

### 4. Hello, World! (Class-based Views)

In `pages/views.py`:

python

```
from django.views.generic import TemplateView

# Renders the homepage template                    
class HomePageView(TemplateView):                     #function for homepage
    template_name = 'home.html'

# Renders the about page template
class AboutPageView(TemplateView):                    #function for aboutpage
    template_name = 'about.html'
```

---

### 5. Templates

Inside your app, create a folder: `pages/templates/`

Add `home.html`:

html

```
<h1>Welcome to the Homepage</h1>
```

![image](https://github.com/user-attachments/assets/0c5db5ad-9f19-40ca-a48c-c5a20f6111ee)


Add `about.html`:

html

```
<h1>About This Project</h1>
```
![image](https://github.com/user-attachments/assets/0c8ab15b-c940-4e1a-ae36-7e3d94c21d12)


---

### 6. Git

**Initialize a Git repository**

bash

```
git init
```

**Create a `.gitignore` file**

bash

```
echo "__pycache__/
*.pyc
db.sqlite3
.env
" > .gitignore
```

**Add and commit**

bash

```
git add .
git commit -m "Initial commit"
```

---

### 7. Optional: GitHub

**Create a new repo on GitHub**, then:

bash

```
git remote add origin https://github.com/your-username/django-pages-app.git
git branch -M main
git push -u origin main
```


---


# Chapter 3: Message Board App with Django Admin

-  In this chapter wewill use a database for the first time to build a basic Message Board application where users can post and read short messages.
-  We’ll explore Django’s powerful built-in admin interface which provides a visual way to make changes to our data.
-  A beginner-friendly Django application where users can post and read short messages.
-   We'll explore Django’s ORM, model-view-template architecture, and its powerful built-in admin interface.


### Additional: 

- Thanks to the powerful Django ORM (Object-Relational Mapper), there is built-in support for multiple database backends: PostgreSQL, MySQL, MariaDB, Oracle, or SQLite.

- This means that we, as developers, can write the same Python code in a models.py file and it will automatically be translated into each database correctly.

-  The only configuration required is to update the DATABASES64 section of our config/settings.py file.
  
-   This is truly an impressive feature, For localdevelopment,Django defaults to using SQLite65 because it is file-based and therefore far simpler to use than the other database options, which require a dedicated server to be running separate from Django itself.

---

#  Algorithm

1. Set up a new Django project.
2. Create a new app called `board`.
3. Define a `Message` model with `name`, `content`, and `timestamp`.
4. Register the model in `admin.py`.
5. Configure URL routing.
6. Create views to list and post messages.
7. Add templates for displaying and adding messages.
8. Use Django Admin to manage messages visually.
9. Test and run the server.

---

# Step-by-Step Guide

### 1. Initial Setup

bash

```
django-admin startproject messageboard_project           #start project
cd messageboard_project                                  
python manage.py startapp board                           #create app
```

Add `board` to `INSTALLED_APPS` in `settings.py`.

python

```
# messageboard_project/settings.py
INSTALLED_APPS = [
    ...
    'board',                                #Register app
]
```

---

### 2. Create the Message Model

python

```
# board/models.py
from django.db import models

class Message(models.Model):                               # Here is where we declare name,content,time
    name = models.CharField(max_length=50)                              # Name of the user
    content = models.TextField()                                         # The actual message
    timestamp = models.DateTimeField(auto_now_add=True)                # Auto-added time

    def __str__(self):
        return f"{self.name}: {self.content[:20]}"                     # First 20 chars as preview

```

### Run migrations:

bash

```
python manage.py makemigrations
python manage.py migrate
```

---

### 3. Enable Django Admin

Create a superuser:

bash

```
python manage.py createsuperuser           

```

Register the model:

python

```
# board/admin.py
from django.contrib import admin
from .models import Message

admin.site.register(Message)             #register the message
```

---

### 4. Create Views

python 

```
# board/views.py
from django.shortcuts import render, redirect
from .models import Message
from django.utils import timezone

def home(request):
z    messages = Message.objects.order_by('-timestamp')                  # Show latest first
    return render(request, 'board/home.html', {'messages': messages})

def post_message(request):
    if request.method == 'POST':                            #gets values from user
        name = request.POST['name']                         #gets the name of user and assign them
        content = request.POST['content']                   #gets the content from user and assign them
        Message.objects.create(name=name, content=content, timestamp=timezone.now())   #auto assign time of user's post
        return redirect('home')                             #return user to home page
    return render(request, 'board/post_message.html')        #add the user post
```

---

### 5. URLs

Create a `urls.py` in `board` app:

python

```
# board/urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),                             #url of home page in app
    path('post/', views.post_message, name='post_message'),        #url of post page in app         
]
```

Connect it to the project’s URL config:

python

```
# messageboard_project/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('board.urls')),                      #url of app
]
```

---

### 6. Templates

Create a folder `templates/board/` and add:

**home.html**

html

```
<!DOCTYPE html>
<html>
<head>
    <title>Message Board</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f0f4f8;
            margin: 0;
            padding: 40px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        h1 {
            color: #2c3e50;
            margin-bottom: 30px;
        }

        a {
            background-color: #3498db;
            color: white;
            padding: 10px 15px;
            text-decoration: none;
            border-radius: 6px;
            font-weight: bold;
            margin-bottom: 30px;
            display: inline-block;
            transition: background-color 0.3s ease;
        }

        a:hover {
            background-color: #2c80b4;
        }

        ul {
            list-style: none;
            padding: 0;
            max-width: 600px;
            width: 100%;
        }

        li {
            background-color: #fff;
            padding: 15px 20px;
            border-radius: 8px;
            margin-bottom: 12px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
            font-size: 16px;
        }

        li strong {
            color: #34495e;
        }

        li em {
            color: #888;
            font-size: 13px;
            margin-left: 8px;
        }
    </style>
</head>
<body>
    <h1>Message Board</h1>
    <a href="{% url 'post_message' %}">Post a Message</a>
    <ul>
      {% for msg in messages %}
        <li>
          <strong>{{ msg.name }}</strong>: {{ msg.content }}
          <em>({{ msg.timestamp }})</em>
        </li>
      {% empty %}
        <li>No messages yet.</li>
      {% endfor %}
    </ul>
</body>
</html>

```

![image](https://github.com/user-attachments/assets/c0e2356d-0e63-4581-9395-41f5df2e86f3)


**post\_message.html**

html

```
<!DOCTYPE html>
<html>
<head>
    <title>Post a Message</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f3f6fb;
            margin: 0;
            padding: 40px;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .form-container {
            background-color: #ffffff;
            padding: 30px 40px;
            border-radius: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 500px;
        }

        h1 {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 25px;
        }

        label {
            display: block;
            margin-top: 15px;
            margin-bottom: 5px;
            color: #333;
            font-weight: bold;
        }

        input[type="text"],
        textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 6px;
            box-sizing: border-box;
            resize: vertical;
            font-size: 14px;
        }

        textarea {
            min-height: 100px;
        }

        button {
            width: 100%;
            padding: 12px;
            background-color: #3498db;
            color: white;
            border: none;
            border-radius: 6px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 20px;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #2c80b4;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h1>Post a Message</h1>
        <form method="post">
            {% csrf_token %}
            <label>Name:</label>
            <input type="text" name="name" required>

            <label>Message:</label>
            <textarea name="content" required></textarea>

            <button type="submit">Post</button>
        </form>
    </div>
</body>
</html>

```

![image](https://github.com/user-attachments/assets/bef95c03-42aa-41b3-8c07-273081cff962)


---

### 7. Run Server and Use Admin

bash

```
python manage.py runserver
```

* Visit `/` to see messages
* Visit `/post/` to add a message
* Visit `/admin/` to manage data with the superuser account

---

##  .gitignore

Create `.gitignore`:

gitignore

```
__pycache__/
*.pyc
db.sqlite3
.env
```


---

##  GitHub Steps

bash

```
git init
git add .
git commit -m "Initial commit for Message Board App"
gh repo create messageboard-app --public --source=. --remote=origin
git push -u origin main
```

---

# structure of code

![image](https://github.com/user-attachments/assets/d02d63c0-db9c-413a-ad7a-c017b97b33e4)



---

# Chapter 4: Django Blog App 

This guide builds a basic blog app in Django that:

* Lists all blog posts on the homepage
* Has a clean UI using inline CSS
* Does not include user login, registration, or post creation via form
* we will add new features in upcoming lessons

---

## 1. Set up the project

bash

```
# Create project folder
mkdir django-blog
cd django-blog


# Create a Django project
django-admin startproject myblog .

# Create a blog app
python manage.py startapp blog
```
## Then create templates into the django-blog

---

## 2. Update settings.py

Open `myblog/settings.py` and make the following changes:

### Add the blog app to installed apps

python

```
INSTALLED_APPS = [
    ...
    'blog',  # Enables the blog app
]
```

### Configure templates directory

```python
import os  # Required for BASE_DIR path handling

TEMPLATES = [
    {
        ...
        'DIRS': [os.path.join(BASE_DIR, 'templates')],  # Adds global templates folder
        'APP_DIRS': True,  # Enables app-specific templates
        ...
    },
]
```

---

## 3. Define the BlogPost model

In `blog/models.py


python

```
from django.db import models  # Import Django's model module

class BlogPost(models.Model):  # Defines the blog post model
    title = models.CharField(max_length=200)  # Title of the post
    content = models.TextField()  # Content of the post
    created_at = models.DateTimeField(auto_now_add=True)  # Timestamp

    def __str__(self):
        return self.title  # Display post title in admin
```

### Make and apply migrations

bash

```
python manage.py makemigrations
python manage.py migrate
```

---

## 4. Create a view

In `blog/views.py`:

python

```
from django.shortcuts import render  # Imports render shortcut
from .models import BlogPost  # Imports the BlogPost model

def home(request):
    posts = BlogPost.objects.all()  # Fetch all blog posts
    return render(request, 'home.html', {'posts': posts})  # Render template with posts
```

---

## 5. Configure URLs

### In `myblog/urls.py`:

python

```
from django.contrib import admin
from django.urls import path
from blog.views import home  # Import home view

urlpatterns = [
    path('admin/', admin.site.urls),  # Admin route
    path('', home, name='home'),  # Home page route
]
```

---

## 6. Create the template

### Create folder:

```
django-blog/
└── templates/
    └── home.html
```

### Create `home.html`:

html
```

{% load static %}
<!DOCTYPE html>
<html>
<head>
    <title>My Blog</title>
    <style>
        /* Inline CSS to style the page */
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            color: #333;
            margin: 0;
            padding: 0;
        }

        .container {
            max-width: 800px;
            margin: 40px auto;
            background: white;
            padding: 20px 30px;
            border-radius: 8px;
            box-shadow: 0 5px 10px rgba(0,0,0,0.05);
        }

        h1 {
            text-align: center;
            margin-bottom: 20px;
            color: #444;
        }

        ul {
            list-style: none;
            padding: 0;
        }

        li {
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid #ddd;
        }

        li strong {
            display: block;
            font-size: 18px;
            margin-bottom: 5px;
            color: #0066cc;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>All Blog Posts</h1>
        <ul>
            {% for post in posts %}
                <li>
                    <strong>{{ post.title }}</strong> <!-- Post title -->
                    {{ post.content }} <!-- Post content -->
                </li>
            {% empty %}
                <li>No posts available.</li> <!-- Message if no posts -->
            {% endfor %}
        </ul>
    </div>
</body>
</html>
```

---

## 7. Register model in admin

In `blog/admin.py`:

python

```
from django.contrib import admin
from .models import BlogPost  # Import the BlogPost model

admin.site.register(BlogPost)  # Register model with Django admin
```

Create a superuser to log in:

bash

```
python manage.py createsuperuser
```

---

## 8. Run the server


## before you run the server check if the structure of your directory matches this following image,

![image](https://github.com/user-attachments/assets/97ac74e2-4d04-4257-83f8-5f22a2f1f3a5)


bash

```
python manage.py runserver
```

Visit:

* [http://127.0.0.1:8000/](http://127.0.0.1:8000/) to see your homepage
* [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin) to add posts




---

## 9. Optional: Create `.gitignore`

Create a `.gitignore` file in the root directory:

gitignore

```
venv/
__pycache__/
*.pyc
*.sqlite3
.env
```

---

## 10. Push to GitHub (additional)

```bash
git init
git add .
git commit -m "Initial Django blog setup with inline CSS"
git remote add origin https://github.com/yourusername/django-blog.git
git push -u origin main
```

---

![image](https://github.com/user-attachments/assets/ba5f3f73-d755-4104-b774-d97989784f0d)



# Chapter 5: Forms in django


To learn forms in django we will be adding customize add page in blog app for users adds **Create, Edit, and Delete** functionality to your existing Django Blog app using Django forms and custom HTML templates, with inline CSS and code comments for clarity.

---

# Django Blog App – Add Create, Edit, Delete (with Forms)

This guide continues from your existing read-only blog. We will:

* Add views for creating, editing, and deleting posts
* Create custom HTML templates for each
* Use Django’s `ModelForm` to handle forms
* Templates use inline CSS
* URLs named for easy access: `post_create`, `post_edit`, `post_delete`
`

---

## 1. Create a Django Form

In `blog/forms.py` (create the file if it doesn't exist):

```python
from django import forms  # Django's forms module
from .models import BlogPost  # Import the BlogPost model

class BlogPostForm(forms.ModelForm):
    class Meta:
        model = BlogPost  # Link form to BlogPost model
        fields = ['title', 'content']  # Include these fields in the form
```

---

## 2. Update Views for CRUD

In `blog/views.py`, import necessary tools:

```python
from django.shortcuts import render, get_object_or_404, redirect
from .models import BlogPost
from .forms import BlogPostForm
```

### View to create a new post

```python
def post_create(request):
    if request.method == 'POST':
        form = BlogPostForm(request.POST)  # Bind data to form
        if form.is_valid():
            form.save()  # Save post to DB
            return redirect('home')  # Redirect to homepage
    else:
        form = BlogPostForm()  # Show empty form
    return render(request, 'post_form.html', {'form': form, 'action': 'Create'})
```

### View to edit an existing post

```python
def post_edit(request, pk):
    post = get_object_or_404(BlogPost, pk=pk)  # Get post or 404
    if request.method == 'POST':
        form = BlogPostForm(request.POST, instance=post)  # Bind data to existing instance
        if form.is_valid():
            form.save()
            return redirect('home')
    else:
        form = BlogPostForm(instance=post)
    return render(request, 'post_form.html', {'form': form, 'action': 'Edit'})
```

### View to delete a post

```python
def post_delete(request, pk):
    post = get_object_or_404(BlogPost, pk=pk)
    if request.method == 'POST':
        post.delete()  # Delete post
        return redirect('home')
    return render(request, 'post_confirm_delete.html', {'post': post})
```

---

## 3. Update `urls.py`

In `myblog/urls.py`:

```python
from django.contrib import admin
from django.urls import path
from blog.views import home, post_create, post_edit, post_delete

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', home, name='home'),  # Home page
    path('post/new/', post_create, name='post_create'),  # Create
    path('post/<int:pk>/edit/', post_edit, name='post_edit'),  # Edit
    path('post/<int:pk>/delete/', post_delete, name='post_delete'),  # Delete
]
```

---

## 4. Update Templates

### `templates/home.html`

Update your homepage template to include **edit/delete links** and a **create button**.

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Blog</title>
    <style>
        body { font-family: sans-serif; background: #f4f4f4; margin: 0; padding: 0; }
        .container { max-width: 800px; margin: 40px auto; background: #fff; padding: 30px; border-radius: 8px; }
        h1 { text-align: center; }
        a.button { background: #28a745; color: white; padding: 8px 12px; text-decoration: none; border-radius: 4px; }
        a.button:hover { background: #218838; }
        .post-actions { margin-top: 5px; }
        .post-actions a { margin-right: 10px; color: #007bff; }
        .post-actions a:hover { text-decoration: underline; }
    </style>
</head>
<body>
<div class="container">
    <h1>All Blog Posts</h1>
    <a href="{% url 'post_create' %}" class="button">Create New Post</a>
    <ul>
        {% for post in posts %}
            <li>
                <strong>{{ post.title }}</strong><br>
                {{ post.content }}
                <div class="post-actions">
                    <a href="{% url 'post_edit' post.pk %}">Edit</a>
                    <a href="{% url 'post_delete' post.pk %}">Delete</a>
                </div>
            </li>
        {% empty %}
            <li>No posts available.</li>
        {% endfor %}
    </ul>
</div>
</body>
</html>
```


![image](https://github.com/user-attachments/assets/ad7250a1-58a2-445f-b350-7bb6eba5efc2)



---

### `templates/post_form.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>{{ action }} Post</title>
    <style>
        body { font-family: sans-serif; background: #f5f5f5; }
        .container { max-width: 600px; margin: 50px auto; background: white; padding: 30px; border-radius: 10px; }
        form label { display: block; margin-top: 15px; }
        form input, form textarea { width: 100%; padding: 8px; margin-top: 5px; }
        button { margin-top: 20px; padding: 10px 15px; background: #007bff; color: white; border: none; border-radius: 4px; }
        button:hover { background: #0056b3; }
        a { text-decoration: none; color: #007bff; }
    </style>
</head>
<body>
<div class="container">
    <h1>{{ action }} Post</h1>
    <form method="post">
        {% csrf_token %}
        {{ form.as_p }} <!-- Renders form fields with <p> tags -->
        <button type="submit">{{ action }}</button>
    </form>
    <br>
    <a href="{% url 'home' %}">Back to home</a>
</div>
</body>
</html>
```


![image](https://github.com/user-attachments/assets/c54003b8-29b1-400c-a1f5-23a6343740c3)


---

### `templates/post_confirm_delete.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Delete Post</title>
    <style>
        body { font-family: sans-serif; background: #f5f5f5; }
        .container { max-width: 600px; margin: 100px auto; background: white; padding: 30px; border-radius: 10px; text-align: center; }
        button { margin-top: 20px; padding: 10px 15px; background: #dc3545; color: white; border: none; border-radius: 4px; }
        button:hover { background: #c82333; }
        a { display: block; margin-top: 20px; color: #007bff; }
    </style>
</head>
<body>
<div class="container">
    <h2>Are you sure you want to delete this post?</h2>
    <p><strong>{{ post.title }}</strong></p>
    <form method="post">
        {% csrf_token %}
        <button type="submit">Yes, Delete</button>
    </form>
    <a href="{% url 'home' %}">Cancel</a>
</div>
</body>
</html>
```


![image](https://github.com/user-attachments/assets/e7c1ec7b-da07-42a0-bfde-32f1ee8bfc2e)



---

## 5. Git Commands(additional)

```bash
git add .
git commit -m "Add create, edit, delete functionality with custom forms and templates"
git push
```
---

# Chapter 6:  Newspaper App

we have build three apps induvial for more understanding one has home,about pages which has links and about the app which is connected with following article app which will have options to create a new article and  update delete and comment on existing articles and finally the accounts app that can have password login security and user accounts. 

## Pages app

---

## Purpose of the `pages` App

* Display static content (homepage, about page, etc.)
* No models or forms
* Uses `TemplateView` for simplicity

---

##  Step-by-Step Guide

###  1. Create the App

Run this in your terminal:

```bash
python manage.py startapp pages
```

---

###  2. Register the App

In `settings.py` under `INSTALLED_APPS`:

```python
INSTALLED_APPS = [
    ...
    'pages',
]
```

---

###  3. Define URLs for Pages

**`pages/urls.py`** (create this file):

```python
from django.urls import path
from .views import HomePageView, AboutPageView

urlpatterns = [
    path('', HomePageView.as_view(), name='home'),
    path('about/', AboutPageView.as_view(), name='about'),
]
```

**Update main `urls.py`** in `newspaperapp/urls.py`:

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('pages.urls')),  # this makes / and /about/ work
]
```

---

###  4. Add Views

**`pages/views.py`**:

```python
from django.views.generic import TemplateView

class HomePageView(TemplateView):
    template_name = 'pages/home.html'

class AboutPageView(TemplateView):
    template_name = 'pages/about.html'
```

---

###  5. Create Templates

Create these folders if they don't exist:

```
/templates/pages/home.html
/templates/pages/about.html
```

---

####  `home.html`

```django
{% extends 'base.html' %}
{% block title %}Home{% endblock %}
{% block content %}
  <h1>Welcome to the Newspaper App</h1>
  <p>This is the homepage.</p>
{% endblock %}
```

---

####  `about.html`

```django
{% extends 'base.html' %}
{% block title %}About{% endblock %}
{% block content %}
  <h1>About Us</h1>
  <p>This is a Django project for practicing static pages.</p>
{% endblock %}
```

---

###  6. Shared Base Template (Optional but Recommended)

Place in: `/templates/base.html`

```django
<!DOCTYPE html>
<html>
<head>
    <title>{% block title %}Newspaper App{% endblock %}</title>
</head>
<body>
    <nav>
        <a href="/">Home</a>
        <a href="/about/">About</a>
    </nav>

    <hr>
    <div class="container">
        {% block content %}{% endblock %}
    </div>

    <footer>
        <p>&copy; 2025 Newspaper App</p>
    </footer>
</body>
</html>
```

---

###  7. Configure Template Settings

In `settings.py`:

```python
TEMPLATES = [
    {
        ...
        'DIRS': [BASE_DIR / "templates"],  # include this line
        ...
    },
]
```

---






## Ariticle app

## 1. Models

`articles/models.py`

python

```
from django.db import models
from django.urls import reverse

class Article(models.Model):
    title           = models.CharField(max_length=200)
    content         = models.TextField()
    published_date  = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.title

    def get_absolute_url(self):              # lets admin “View on site”
        return reverse('article_detail', kwargs={'pk': self.pk})


class Comment(models.Model):
    article    = models.ForeignKey(Article, on_delete=models.CASCADE,
                                   related_name='comments')
    name       = models.CharField(max_length=100)
    body       = models.TextField()
    created_at = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return f'Comment by {self.name}'
```

bash
```
python manage.py makemigrations
python manage.py migrate
```

---

## 2. Forms

`articles/forms.py`

python

```
from django import forms
from .models import Comment, Article

class CommentForm(forms.ModelForm):
    class Meta:
        model  = Comment
        fields = ['name', 'body']


class ArticleForm(forms.ModelForm):     # for create / edit
    class Meta:
        model  = Article
        fields = ['title', 'content']
```

---

## 3. Views

`articles/views.py`

python

```
from django.views.generic import (ListView, DetailView,
                                  CreateView, UpdateView, DeleteView)
from django.shortcuts import redirect
from django.urls import reverse_lazy

from .models import Article
from .forms import CommentForm, ArticleForm


class ArticleListView(ListView):
    model               = Article
    template_name       = 'articles/articles_list.html'
    context_object_name = 'articles'
    ordering            = ['-published_date']


class ArticleCreateView(CreateView):
    model         = Article
    form_class    = ArticleForm
    template_name = 'articles/article_form.html'   # reused for edit


class ArticleUpdateView(UpdateView):
    model         = Article
    form_class    = ArticleForm
    template_name = 'articles/article_form.html'   # same fields


class ArticleDeleteView(DeleteView):
    model         = Article
    template_name = 'articles/article_delete.html'
    success_url   = reverse_lazy('articles')


class ArticleDetailView(DetailView):
    model               = Article
    template_name       = 'articles/article_detail.html'
    context_object_name = 'article'

    # handle comment POST
    def post(self, request, *args, **kwargs):
        self.object = self.get_object()
        form = CommentForm(request.POST)
        if form.is_valid():
            comment = form.save(commit=False)
            comment.article = self.object
            comment.save()
        return redirect('article_detail', pk=self.object.pk)

    def get_context_data(self, **kwargs):
        context = super().get_context_data(**kwargs)
        context['form']     = CommentForm()
        context['comments'] = self.object.comments.all().order_by('-created_at')
        return context
```

---

## 4. URLs

`articles/urls.py`

python

```
from django.urls import path
from .views import (
    ArticleListView, ArticleCreateView, ArticleUpdateView,
    ArticleDeleteView, ArticleDetailView,
)

urlpatterns = [
    path('articles/',                      ArticleListView.as_view(),  name='articles'),
    path('articles/new/',                  ArticleCreateView.as_view(), name='article_create'),
    path('article/<int:pk>/',              ArticleDetailView.as_view(), name='article_detail'),
    path('article/<int:pk>/edit/',         ArticleUpdateView.as_view(), name='article_edit'),
    path('article/<int:pk>/delete/',       ArticleDeleteView.as_view(), name='article_delete'),
]

```

In **project** `urls.py`:

python

```
from django.urls import path, include
urlpatterns = [
    path('', include('articles.urls')),
    path('admin/', include('django.contrib.admin.urls')),
]
```

---

## 5. Templates (minimal versions)

All extend `base.html` from earlier.

### 5.1 `articles/articles_list.html`

django

```
{% extends 'base.html' %}
{% block title %}Articles{% endblock %}
{% block content %}
<h2>Latest Articles</h2>
<a href="{% url 'article_create' %}">➕ New Article</a>
{% for article in articles %}
  <h3><a href="{% url 'article_detail' article.pk %}">{{ article.title }}</a></h3>
  <p>{{ article.content|truncatewords:25 }}</p>
{% empty %}
  <p>No articles yet.</p>
{% endfor %}
{% endblock %}
```

### 5.2 `articles/article_form.html`  (create & edit)

django

```
{% extends 'base.html' %}
{% block title %}{{ view.object|yesno:"Edit Article,New Article" }}{% endblock %}
{% block content %}
<h2>{{ view.object|yesno:"Edit Article,New Article" }}</h2>
<form method="post">{% csrf_token %}{{ form.as_p }}
  <button type="submit">Save</button>
</form>
{% endblock %}
```

### 5.3 `articles/article_delete.html`

html

```
{% extends 'base.html' %}
{% block content %}
<h2>Delete Article</h2>
<p>Are you sure you want to delete “{{ article.title }}”?</p>
<form method="post">{% csrf_token %}<button type="submit">Yes, delete</button></form>
<a href="{% url 'article_detail' article.pk %}">Cancel</a>
{% endblock %}
```

### 5.4 `articles/article_detail.html`

html

```
{% extends 'base.html' %}
{% block title %}{{ article.title }}{% endblock %}
{% block content %}
<h1>{{ article.title }}</h1>
<p>{{ article.content }}</p>

<a href="{% url 'article_edit' article.pk %}">✏️ Edit</a>
<a href="{% url 'article_delete' article.pk %}">🗑 Delete</a>

<hr>
<h3>Comments ({{ comments|length }})</h3>
{% for c in comments %}
  <p><strong>{{ c.name }}</strong> – {{ c.created_at|date:"Y-m-d H:i" }}<br>{{ c.body }}</p>
{% empty %}<p>No comments yet.</p>{% endfor %}

<hr>
<h3>Leave a comment</h3>
<form method="post">{% csrf_token %}{{ form.as_p }}
  <button type="submit">Post</button>
</form>
{% endblock %}
```

---

## 6. Admin Registration (optional)

`articles/admin.py`

python

```
from django.contrib import admin
from .models import Article, Comment

@admin.register(Article)
class ArticleAdmin(admin.ModelAdmin):
    list_display = ('title', 'published_date')
    search_fields = ('title',)

@admin.register(Comment)
class CommentAdmin(admin.ModelAdmin):
    list_display = ('article', 'name', 'created_at')
    search_fields = ('name', 'body')
```

---

## 7. Permissions (Optional Tweaks)

* Wrap edit/delete buttons with `{% if user.is_authenticated %}` or author‑check.
* Switch `ArticleCreateView`/`ArticleUpdateView` to `LoginRequiredMixin` and `UserPassesTestMixin` if desired.

---

## 8. Testing Flow

1. `python manage.py runserver`
2. Visit `/articles/` → create an article.
3. Click an article → detail view shows content.
4. Test **Edit**, **Delete** links.
5. Post a comment—should appear instantly.
6. Try the admin “View on site” action (works via `get_absolute_url`).


---

#  Chapter 7: User Authentication and password management

- To learn about basic authentication system  we'll integrate the following into our blog app:

* **User Login**
* **User Logout**
* **User signup**
  

---

## 1. Update `settings.py`

Add this to the **bottom** of `myblog/settings.py`:

python
```
# Redirect after login/logout
LOGIN_REDIRECT_URL = '/'
LOGOUT_REDIRECT_URL = '/'
```

---

##  2. Add Auth URLs to Main `urls.py`

In `myblog/urls.py`, import Django’s auth views and add paths:

python
```

from django.contrib import admin
from django.urls import path, include
from django.contrib.auth import views as auth_views
from django.contrib.auth.views import LogoutView

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('blog.urls')),
    path('login/', auth_views.LoginView.as_view(template_name='blog/login.html'), name='login'),
    path('logout/', auth_views.LogoutView.as_view(), name='logout'),
    path('logout/', LogoutView.as_view(), name='logout'),
]

```

---

## 3. Add Registration URL
In blog/urls.py:

python
```
from . import views

urlpatterns = [
    path('', views.home, name='blog-home'),
    path('add/', views.create_post, name='create-post'),
    path('register/', views.register, name='register'),
]

```

---

##  4. Protect "Add Post" View (Login Required)

Update view in `blog/views.py` to require login and signup:

python
```
from django.shortcuts import render, redirect
from .models import Post
from .forms import PostForm
from django.contrib.auth.decorators import login_required
from django.contrib.auth import login
from django.contrib.auth.forms import AuthenticationForm
from .forms import RegisterForm

def home(request):
    posts = Post.objects.all()
    return render(request, 'blog/home.html', {'posts': posts})


def register(request):
    if request.method == 'POST':
        form = RegisterForm(request.POST)
        if form.is_valid():
            user = form.save()
            login(request, user)  # Automatically log in new user
            return redirect('blog-home')
    else:
        form = RegisterForm()
    return render(request, 'blog/register.html', {'form': form})


@login_required

def create_post(request):
    if request.method == 'POST':
        form = PostForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect('blog-home')
    else:
        form = PostForm()
    return render(request, 'blog/create_post.html', {'form': form})


```

---


##  5. Create a Registration Form
In blog/forms.py, add a registration form using Django's built-in UserCreationForm:

 ```
from django import forms
from .models import Post
from django.contrib.auth.forms import UserCreationForm
from django.contrib.auth.models import User


class PostForm(forms.ModelForm):
    class Meta:
        model = Post
        fields = ['title', 'content', 'author']


class RegisterForm(UserCreationForm):
    email = forms.EmailField(required=True)
    class Meta:
        model = User
        fields = ['username', 'email', 'password1', 'password2']

 ```


##  6. Show Login/Logout and signup in Navbar 

Update `blog/templates/blog/home.html` to show login/logout and signup:
html
```
<!DOCTYPE html>
<html>
<head>
    <title>Blog Home</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f9f9f9;
            
        }

        h1 {
            color: #333;
            margin-bottom: 20px;
        }

        .post {
            background: #fff;
            border: 1px solid #ddd;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 8px;
        }

        .post h2 {
            margin: 0;
            color: #2c3e50;
        }

        .post small {
            color: #888;
        }

        a.button {
            display: inline-block;
            padding: 10px 15px;
            background-color: #007bff;
            color: white;
            text-decoration: none;
            border-radius: 4px;
            margin-bottom: 20px;
        }

        a.button:hover {
            background-color: #0056b3;
        }


    </style>
</head>
<body>
        <h1>Blog Posts</h1>

   {% if user.is_authenticated %}
    <p>Welcome, {{ user.username }}! 
    <form method="post" action="{% url 'logout' %}">
    {% csrf_token %}
    <button type="submit">Logout</button>
    </form>
{% else %}
    <a href="{% url 'login' %}" class="button">Login</a><br>
    <a href="{% url 'register' %}" class="button" style="background-color: #4947a8;">Register</a>
    
{% endif %}

    <hr>
    
    {% for post in posts %}
        <div class="post">
            <h2>{{ post.title }}</h2>
            <p>{{ post.content }}</p>
            <small>By {{ post.author }} on {{ post.date_posted }}</small>
        </div>
    {% empty %}
        <p>No posts yet.</p>
    {% endfor %}
</body>
</html>

```

---
---
##  3. Create Login Template

**Path:** `blog/templates/blog/login.html`

html
```
<!DOCTYPE html>
<html>
<head>
    <title>Login</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f4f4f4;
        }

        form {
            background: #fff;
            padding: 25px;
            border: 1px solid #ddd;
            border-radius: 8px;
            max-width: 400px;
        }

        button {
            padding: 10px 15px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
        }

        a {
            margin-top: 15px;
            display: inline-block;
        }
    </style>
</head>
<body>
    <h1>Login</h1>

    <form method="post">
        {% csrf_token %}
        {{ form.as_p }}
        <button type="submit">Log in</button>
    </form>
</body>
</html>
```
---

## 6. Create a sign up templates:

```
<!DOCTYPE html>
<html>
<head>
    <title>Register</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f4f4f4;
        }

        form {
            background: #fff;
            padding: 25px;
            border: 1px solid #ddd;
            border-radius: 8px;
            max-width: 400px;
        }

        button {
            padding: 10px 15px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 4px;
        }

        a {
            margin-top: 15px;
            display: inline-block;
        }
    </style>
</head>
<body>
    <h1>Register</h1>

    <form method="post">
        {% csrf_token %}
        {{ form.as_p }}
        <button type="submit">Sign Up</button>
    </form>

    <a href="{% url 'login' %}">Already have an account? Log in</a><br>
    <a href="{% url 'blog-home' %}">← Back to Home</a>
</body>
</html>

```

---
##  6. Create a User to Test
bash
```
python manage.py createsuperuser
```
try and test the webpage you have created

##  Structure of blog app after adding all the above given features

![image](https://github.com/user-attachments/assets/03f6cad0-50f4-46c2-86cf-519a6aff12be)

 ---


## To learn about more clear flow of authentication and password management we will intergerate the following features into our pre existing Newspaper app in chapter 6.All using custom templates/pages, not the default Django ones,

* **User signup**
* **Login**
* **Logout**
* **Password change**
* **Password reset**


---

##  Step 1: Project Setup

### 1.1 Ensure your app is ready

If you haven’t created the app:

bash

```
python manage.py startapp accounts
```

### 1.2 Add `accounts` to `INSTALLED_APPS` in `settings.py`:

python

```
INSTALLED_APPS = [
    ...
    'accounts',
    'django.contrib.auth',
    'django.contrib.messages',
    ...
]
```

### 1.3 Configure `TEMPLATES` and `STATICFILES_DIRS` if needed:

Ensure your `TEMPLATES` setting looks like this:

python

```
TEMPLATES = [
    {
        ...
        'DIRS': [BASE_DIR / 'templates'],  # global templates dir
        ...
    },
]
```

---

## ✅ Step 2: Create URLs

### 2.1 In `accounts/urls.py`:

python

```
from django.urls import path
from . import views  
from django.contrib.auth import views as auth_views
from .views import HomePageView

urlpatterns = [
    path('', HomePageView.as_view(), name='base'),
    path('signup/', views.signup_view, name='signup'),
    path('login/', auth_views.LoginView.as_view(template_name='accounts/login.html'), name='login'),
    path('logout/', auth_views.LogoutView.as_view(template_name='accounts/logout.html'), name='logout'),
    path('password_change/', auth_views.PasswordChangeView.as_view(template_name='accounts/password_change.html'), name='password_change'),
    path('password_change/done/', auth_views.PasswordChangeDoneView.as_view(template_name='accounts/password_change_done.html'), name='password_change_done'),
    path('password_reset/', auth_views.PasswordResetView.as_view(template_name='accounts/password_reset.html'), name='password_reset'),
    path('password_reset/done/', auth_views.PasswordResetDoneView.as_view(template_name='accounts/password_reset_done.html'), name='password_reset_done'),
    path('reset/<uidb64>/<token>/', auth_views.PasswordResetConfirmView.as_view(template_name='accounts/password_reset_confirm.html'), name='password_reset_confirm'),
    path('reset/done/', auth_views.PasswordResetCompleteView.as_view(template_name='accounts/password_reset_complete.html'), name='password_reset_complete'),
     path('dashboard/', views.dashboard, name='dashboard'),
]
```

### 2.2 Include `accounts.urls` in your project’s `urls.py`:

python

```

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('accounts/', include('accounts.urls')),
    path('accounts/', include('django.contrib.auth.urls')),
]
```

---

## ✅ Step 3: Create Signup View , homepageview and loginrequired

### 3.1 In `accounts/views.py`:

python

```

from django.contrib.auth.forms import UserCreationForm
from django.shortcuts import render, redirect
from django.views.generic import TemplateView

# Renders the homepage template
class HomePageView(TemplateView):
    template_name = 'base.html'

def signup_view(request):
    if request.method == 'POST':
        form = UserCreationForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect('login')
    else:
        form = UserCreationForm()
    return render(request, 'accounts/signup.html', {'form': form})

from django.contrib.auth.decorators import login_required
from django.shortcuts import render

@login_required
def dashboard(request):
    return render(request, 'accounts/dashboard.html')




```

---

## ✅ Step 4: Create Templates



Note it has internal css

Create the following files in: `templates/accounts/`
(e.g., `myproject/templates/accounts/login.html`, etc.)

### 4.1 Base layout (`templates/base.html`)

html

```
<!DOCTYPE html>
<html>
<head>
     <title>Newspaper Auth</title>


        <style>
        /* General Page Styles */
        body {
            font-family: Arial, sans-serif;
            background-color: #f8f9fa;
            margin: 0;
            padding: 0;
        }

        nav {
            background-color: #343a40;
            padding: 10px 20px;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: flex-start;
        }

        nav form {
            margin: 0 5px;
        }

        nav button {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 8px 12px;
            cursor: pointer;
            border-radius: 4px;
            font-size: 14px;
        }

        nav button:hover {
            background-color: #0056b3;
        }

        hr {
            margin: 0;
            border: none;
            border-top: 1px solid #dee2e6;
        }

        .messages {
            padding: 15px;
            margin: 20px;
            background-color: #e9ecef;
            border-left: 5px solid #007bff;
            font-size: 14px;
        }

       
        main {
            padding: 20px;
        }

        body {
            font-family: 'Segoe UI', sans-serif;
            background-color: #f1f3f5;
            margin: 0;
            padding: 0;
        }

        h2 {
            text-align: center;
            margin-top: 40px;
            color: #343a40;
        }

        form {
            max-width: 400px;
            margin: 30px auto;
            background: white;
            padding: 25px 30px;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        form input[type="text"],
        form input[type="password"],
        form input[type="email"] {
            width: 100%;
            padding: 10px;
            margin: 8px 0 16px 0;
            border: 1px solid #ced4da;
            border-radius: 4px;
            font-size: 14px;
        }

        form button[type="submit"] {
            width: 100%;
            background-color: #007bff;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 4px;
            font-size: 15px;
            cursor: pointer;
        }

        form button[type="submit"]:hover {
            background-color: #0056b3;
        }

        .errorlist {
            color: #dc3545;
            list-style-type: none;
            padding-left: 0;
        }
    </style>
</head>



<body>
    <nav>
        <form method="post" action="{% url 'signup' %}">
    {% csrf_token %}
    <button type="submit">signup</button>
</form>
 |
        <form method="post" action="{% url 'login' %}">
    {% csrf_token %}
    <button type="submit">Login</button>
</form>
|
        <form method="post" action="{% url 'logout' %}">
        {% csrf_token %}
  
        <button type="submit">Logout</button>
        </form>|
        
        <form method="post" action="{% url 'password_change' %}">
    {% csrf_token %}
    <button type="submit">password change</button>
</form>
 |
<form method="post" action="{% url 'password_reset' %}">
    {% csrf_token %}
    <button type="submit">password reset</button>
</form>

     
    </nav>
    <hr>
    {% if messages %}
        {% for message in messages %}
            <p>{{ message }}</p>
        {% endfor %}
    {% endif %}
    {% block content %}{% endblock %}
</body>
</html>
```

### 4.2 Signup (`signup.html`)

html

```
{% extends "base.html" %}
{% block content %}
<h2>Sign Up</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Sign Up</button>
</form>
{% endblock %}
```

### 4.3 Login (`login.html`)

html

```
{% extends "base.html" %}
{% block content %}
<h2>Login</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Login</button>
</form>
{% endblock %}
```

### 4.4 Logout (`logout.html`)

html

```
{% extends "base.html" %}
{% block content %}
<h2>You have been logged out.</h2>
<a href="{% url 'login' %}">Log in again</a>
{% endblock %}
```

### 4.5 Password Change & Done

**password\_change.html**

html

```
{% extends "base.html" %}
{% block content %}
<h2>Change Password</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Change</button>
</form>
{% endblock %}
```

**password\_change\_done.html**

html

```
{% extends "base.html" %}
{% block content %}
<p>Password changed successfully.</p>
{% endblock %}
```

### 4.6 Password Reset

**password\_reset.html**

html

```
{% extends "base.html" %}
{% block content %}
<h2>Reset Your Password</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Send Reset Email</button>
</form>
{% endblock %}
```

**password\_reset\_done.html**

html

```
{% extends "base.html" %}
{% block content %}
<p>Check your email for the reset link.</p>
{% endblock %}
```

**password\_reset\_confirm.html**

html

```
{% extends "base.html" %}
{% block content %}
<h2>Enter new password</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Change password</button>
</form>
{% endblock %}
```

**password\_reset\_complete.html**

html

```
{% extends "base.html" %}
{% block content %}
<p>Your password has been reset. <a href="{% url 'login' %}">Login</a></p>
{% endblock %}
```

**dashboard/./html**


html 
```
{% extends "base.html" %}

{% block title %}Dashboard{% endblock %}

{% block content %}
<div class="dashboard-container">
    <div class="dashboard-header">Welcome to Your Dashboard</div>

    <div class="dashboard-section">
        <h3>Your Profile</h3>
        <p>Name: {{ user.username }}</p>
        <p>Email: {{ user.email }}</p>
    </div>

    <div class="dashboard-section">
        <h3>Actions</h3>
        <a href="#" class="button">Update Profile</a>
        <a href="#" class="button">View Reports</a>
    </div>
</div>
{% endblock %}

```

---

## ✅ Step 5: Email Settings for Reset and Login Redirect

Add to `settings.py` (use console backend for dev):

python

```
EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'

LOGIN_REDIRECT_URL = '/accounts/dashboard/'
```

---

## ✅ Step 6: Migrate , create a superuser & Run

bash

```
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Visit `http://127.0.0.1:8000/accounts/signup/` to start testing.

##  Structure of blog app after adding all the above given features

![image](https://github.com/user-attachments/assets/ce60b01f-7631-4d43-88ab-11bd2bc59cad)

---




