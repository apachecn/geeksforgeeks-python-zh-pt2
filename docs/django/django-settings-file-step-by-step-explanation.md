# 姜戈设置文件-分步说明

> 原文:[https://www . geesforgeks . org/django-设置-文件-逐步说明/](https://www.geeksforgeeks.org/django-settings-file-step-by-step-explanation/)

一旦我们创建了 Django 项目，它就带有预定义的目录结构，其中包含以下文件，每个文件都有自己的用途。

举个例子

```py
// Create a Django Project "mysite" 
django-admin startproject mysite

cd /pathTo/mysite
// Create a Django app "polls" inside project "mysite"
python manage.py startapp polls
```

*在**终端/CMD** 上执行这些命令后，项目“我的网站”的目录结构将是:*

```py
mysite           <-- BASE_DIR      
    --> mysite                 
            -> __init__.py
            -> asgi.py
            -> settings.py    <-- settings.py file 
            -> urls.py
            -> wsgi.py
    --> manage.py
    --> polls
```

### 关于 settings.py 文件的见解

Django 设置文件包含您的 Django 项目的所有配置。本文将讨论 Django 的 settings.py 文件的要点。
一个设置文件只是一个带有模块级变量的 Python 模块。

#### BASE_DIR

BASE_DIR 指向项目的顶层，即**我的站点**，无论我们在项目中定义什么路径都是相对于 BASE_DIR 的。要使用 BASE_DIR，我们必须使用 python 提供的[操作系统模块](https://www.geeksforgeeks.org/os-module-python-examples/)。

```py
BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))
```

#### 调试

在开发中*错误*非常明显的会出现。写一个我们不会遇到任何错误的程序是没有乐趣的。但是有时候处理错误是非常忙乱的。Django 提供了一个内置调试器，这使得开发人员的生活非常轻松。我们可以这样使用:

```py
DEBUG = True  // It is Default value and is preferred in only Development Phase.
```

在生产中，首选 **DEBUG = False** 。

#### ALLOWED_HOSTS

允许的主机列表包含所有可以运行你的姜戈项目的域的地址。

> 当 DEBUG 设置为 True 时
> ALLOWED_HOSTS 可以是空列表**即 ALLOWED_HOSTS=[ ]** ，因为默认情况下是 **127.0.0.1** 或 **localhost**
> 当 DEBUG 设置为 False 时
> ALLOWED_HOSTS 不能是空列表。我们必须在列表中给出主机名称。**即 ALLEVED _ HOSTS =[" 127 . 0 . 0 . 1 "，" *.heroku.com"]** 。“127.0.0.1”代表你的 PC，“*.heroku.com”代表这个应用也可以在 heroku 上运行。

#### 已安装的应用程序

在这一节中，我们提到了将在我们的 Django 项目中使用的所有应用程序。之前我们制作了一个应用程序**民意测验**我们必须告诉姜戈它的存在要做到这一点必须放入 INSTALLED_APPS:

```py
    INSTALLED_APPS = [
        // Some preloaded apps by Django,
        'polls', // don't forget to quote it and also commas after every app
]
```

#### 数据库

Django 官方支持以下数据库:

*   一种数据库系统
*   马里亚 DB
*   关系型数据库
*   神谕
*   T2–默认情况下

```py
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.sqlite3',
            'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
        }
    }
```

还有一些由[第三方](https://docs.djangoproject.com/en/3.0/ref/databases/#third-party-notes)提供的数据库后端。
下面是使用 PostgreSQL
的例子

```py
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': YOUR_DB_NAME,
            'USER': USERNAME,
            'PASSWORD': PASSWORD_FOR_DB,
            'HOST': 'localhost'  // in Development.
        }
    }
```

> 注意:在使用 PostgreSQL 之前，我们必须使用
> pip 安装 psycopg2 来安装 psycopg2

#### 可变网址

URL 变量是相对于 BASE_DIR 的。这些变量用于存储媒体或静态文件。
**注意:在父目录中制作静态和媒体文件夹。**T3】

MEDIA_URL

媒体网址是基本目录的相对路径。该变量用于存储媒体文件。

```py
MEDIA_URL= '/media/'
```

静态网址

静态网址是基本目录的相对路径。这个变量用于存储静态文件。

```py
STATIC_URL = '/static/'
```

#### 根变量

ROOT 变量是绝对路径。这些变量用于检索媒体或静态文件。

媒体 _ROOT

MEDIA_ROOT 是绝对路径。该变量用于检索媒体文件。

```py
MEDIA_ROOT= os.path.join(BASE_DIR, 'media')
```

静态根

STATIC_ROOT 是绝对路径。这个变量用于检索静态文件。

```py
STATIC_ROOT= os.path.join(BASE_DIR, 'static')
```

> 注意:Django 设置中的所有变量名都是大写的。