# Chapter 4: Django Blog App  // (needs to be recreated)

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
<img width="1378" height="404" alt="image" src="https://github.com/user-attachments/assets/5cf317d1-51dc-43c8-bb05-3cd21cf46594" />

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


