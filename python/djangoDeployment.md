[https://uwsgi-docs.readthedocs.io/en/latest/tutorials/Django_and_nginx.html]       

## Preparation      
- Django
- Nginx
- wsgi

## Concept      
the web client <-> the web server <-> the socket <-> uwsgi <-> Django       

```
python manage.py runserver 0.0.0.0:8000

basically equals

uwsgi --http :8000 --module mysite.wsgi

```

## symlink
[https://www.freecodecamp.org/news/symlink-tutorial-in-linux-how-to-create-and-remove-a-symbolic-link/]     
[https://www.geeksforgeeks.org/soft-hard-links-unixlinux/]      
```
ln -s /home/james/transactions.txt trans.txt
rm <path-to-symlink>
-s means soft link
```

## django collectstatic     
[https://blog.csdn.net/weixin_36296538/article/details/83153070]    
[https://www.jianshu.com/p/765296325484]    
[https://rahmonov.me/posts/django-static-files/]        

## file path       
```
relative path: 
polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    urls.py
    views.py
polls/urls.py¶
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]

absolute path:
mysite/urls.py
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]


```
