# Python |使用 django 的 Sessions 框架

> 原文:[https://www . geesforgeks . org/python-sessions-framework-use-django/](https://www.geeksforgeeks.org/python-sessions-framework-using-django/)

**先决条件** : [姜戈安装](https://www.geeksforgeeks.org/django-introduction-and-installation/) | [姜戈介绍](https://www.geeksforgeeks.org/django-introduction-set-2-creating-a-project/)

Sessions 框架可用于为网站中的匿名用户提供持久行为。会话是 Django 使用的机制，您可以根据每个站点的访问者来存储和检索数据。Django 使用包含特殊会话 id 的 cookie。

要在 django 中启用会话，您需要在`settings.py`中确保两件事:

1.  **MIDDLEWARE_CLASSES** 已激活‘django . contrib . sessions . MIDDLEWARE . sessionmiddleware’
2.  **INSTALLED_APPS** 添加了“django.contrib.sessions”。

    ```py
    # Application definition
    INSTALLED APPS = [
    'dhun',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    ]
    MIDDLEWARE = [
    'django.middleware.securitY.SecuritYMiddleware',
    'django.contrib.sessions.middleware.SessionMiddLeware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMidd1eware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
    ]
    ```

启用会话后，必须创建会话数据库表，为此，请运行以下命令:

```py
python manage.py syncdb
```

运行前一个命令后，如果没有发现任何错误，则稍后运行下面给出的命令，最终将保存在迁移文件中的更改反映到数据库中。

```py
python manage.py migrate
```

现在，一旦创建了会话，就必须对 cookies 进行测试。在 `views.py`中，在索引视图中设置测试 cookie，在你的关于视图中测试 cookie。

```py
from django.shortcuts import render
from django.http import HttpResponse
from .models import Album

def home(request) :
    a = Album.objects.all()
    return render(request, "dhun/home.html ", {"Album":a})

def index(request) :
    num_authors = Author.objects.count()
    request.session.set_test_cookie()
    num_visits = request.session.get( 'num_visits', 0)
    request.session ['num_visits'] = num_visits + 1
    context ={
        'num_books':num_books,
        'num_instances':num_instances,
        'num_instances available':num_instances_available,
        'num_authors':num_authors,
        'num_visits':num_visits,
    }

def about(request):
    LANGUAGE_CODE ='en-us '
    TIME_ZONE ='UTC'
    if request.session.test_cookie_worked():
        print ("Cookie Tested !")
        request.session.delete_test_cookie()
```

看到工作完成到现在。

*   首先通过此命令运行 localhost。

    ```py
    python manage.py runserver
    ```

*   然后在浏览器中打开 http://localhost:8000/即可。
*   访问索引页面，然后访问关于页面。“饼干测试！”会被打印到控制台上。

想知道这个网站被访问了多少次。在视图中，您必须做以下两件事。

1.  在索引视图功能中添加和更新代码/li >
2.  更新

    ```py
    from django.shortcuts import render
    from django.http import HttpResponse
    from .models import Album

    def home(request):
        a = AIbum. objects.all()
        return render(request, "dhun/home.html", {"album":a})

    def index(request):
        visits = int(reques.COOKIES.get('visits', '0'))
        response = HttpResponse(template.render(context))

        if request.COOKIES.has_key('last_visit'):
            last_visit = request. COOKIES [ ' last_visit']
            last_visit_time = datetime.strptime(last_visit[:-7], "%Y-%m-%d %H:%M:%S") "
            curr_time = datetime.now()
            if (curr_time—last_visit_time).days > O:
                response.set_cookie( 'visits ', visits + 1)
                response. set_cookie( ' last_visit', datetime.now())
            else :
                response.set_cookie( ' last_visit', datetime.now())
            return response

    def about(request) :
        context = RequestContext(request)
        if request.COOKIES.has_key(' visits '):
            v = request.COOKIES [' visits ']
        else :
            v = 0
        return render_to_response('music/about.html', { 'visits':v}, context)
    ```

    的关于查看功能

参考:[https://docs.djangoproject.com/en/2.1/topics/http/sessions/](https://docs.djangoproject.com/en/2.1/topics/http/sessions/)