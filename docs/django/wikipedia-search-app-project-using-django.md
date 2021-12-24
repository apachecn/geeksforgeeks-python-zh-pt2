# 使用 Django 的维基百科搜索应用项目

> 原文:[https://www . geesforgeks . org/Wikipedia-search-app-project-use-django/](https://www.geeksforgeeks.org/wikipedia-search-app-project-using-django/)

Django 是一个基于 Python 的高级网络框架，允许快速开发和干净、实用的设计。它也被称为电池内置框架，因为 Django 为一切提供内置功能，包括 Django 管理界面、默认数据库——sqllite 3 等。今天我们将在 django 创建一个笑话应用。

在本文中，我们将使用 django 制作维基百科搜索应用程序。在维基百科上搜索，我们将使用 python 中的“维基百科”库。

### 创建姜戈项目–

首先我们必须安装 django

人的本质

```py
pip install django
```

然后安装维基百科库

```py
pip install wikipedia
```

让我们创建新的 django 项目

```py
django-admin startproject wikipedia_app
```

```py
cd wikipedia_app
```

然后在 django 项目中创建新的应用程序

```py
python3 manage.py startapp main
```

然后在**设置中添加应用名称。在 INSTALLED_APPS 中复制**

![](img/cc260895d9b58daab438c41ac83ed888.png)

**view . py**

## 蟒蛇 3

```py
from django.shortcuts import render,HttpResponse
import wikipedia

# Create your views here.
def home(request):
    if request.method == "POST":
        search = request.POST['search']
        try:
            result = wikipedia.summary(search,sentences = 3) #No of sentences that you want as output
        except:
            return HttpResponse("Wrong Input")
        return render(request,"main/index.html",{"result":result})
    return render(request,"main/index.html")
```

创建新目录**模板**里面的创建新目录**主**

在里面创建新文件**index.html**

**index.html**

## 超文本标记语言

```py
<!DOCTYPE html>
<html>
<head>
    <title>GFG</title>
</head>
<body>
    <h1>Wikipedia Search</h1>
    <form method="post">
        {% csrf_token %}
        <input type="text" name="search">
        <button type="submit">Search</button>
    </form>
    {% if result %}
        {{result}}
    {% endif %}
</body>
</html>
```

在主应用内创建新文件**URL . py**

## 蟒蛇 3

```py
from django.urls import path
from .views import *

urlpatterns = [
    path('', home,name="home"),
]
```

**维基百科 _ app/URL . py**

## 蟒蛇 3

```py
from django.contrib import admin
from django.urls import path,include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',include("main.urls")),
]
```

要运行此应用程序，请打开 cmd 或终端

```py
python3 manage.py runserver
```

### **输出:-**

![](img/c2484e0555f69744b82aa0738748c0f5.png)