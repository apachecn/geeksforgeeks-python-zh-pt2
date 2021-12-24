# 姜戈 REST 框架的 JWT 认证

> 原文:[https://www . geesforgeks . org/jwt-authentication-with-django-rest-framework/](https://www.geeksforgeeks.org/jwt-authentication-with-django-rest-framework/)

[JSON 网络令牌](https://www.geeksforgeeks.org/json-web-token-jwt/)是一个开放标准，用于使用 JSON 对象在各方之间安全地传输数据。JWT 用于用户和提供者的无状态身份验证机制，这意味着在客户端维护会话，而不是在服务器上存储会话。这里，我们将在姜戈实现 JWT 认证系统。

**Modules required :**

*   姜戈:[姜戈安装](https://www.geeksforgeeks.org/django-introduction-and-installation/)
*   djgorestframework _ simplejwt:t0]

**基本设置:**

通过以下命令启动项目–

```py
 django-admin startproject config
```

将目录更改为项目配置–

```py
 cd config
```

启动服务器-通过在终端中键入以下命令启动服务器–

```py
 python manage.py runserver
```

要检查服务器是否正在运行，请转到网络浏览器，输入 *http://127.0.0.1:8000/* 作为网址。

现在按停止服务器

```py
ctrl-c
```

**我们现在创建一个名为“app”的应用。**

```py
python manage.py startapp app
```

![](img/7c2438215b40f72c05098dafba0e5331.png)

**向 settings.py 文件添加配置:**

打开 config 文件夹中的 settings.py 文件并添加配置。

```py
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```

**编辑 URL . py 文件**
在配置文件夹中打开 URL . py

```py
from django.urls import path, include
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    path('api/token/',
         jwt_views.TokenObtainPairView.as_view(),
         name ='token_obtain_pair'),
    path('api/token/refresh/',
         jwt_views.TokenRefreshView.as_view(),
         name ='token_refresh'),
    path('', include('app.urls')),
]
```

**编辑 view . py**
打开 app 文件夹中的 view . py，制作一个 API 视图

```py
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework.permissions import IsAuthenticated

class HelloView(APIView):
    permission_classes = (IsAuthenticated, )

    def get(self, request):
        content = {'message': 'Hello, GeeksforGeeks'}
        return Response(content)
```

**编辑 URL . py**
在 app 文件夹中创建一个 URL . py 并进行编辑

```py
from django.urls import path
from . import views

urlpatterns = [
    path('hello/', views.HelloView.as_view(), name ='hello'),
]
```

用法:

为了发出一个 HTTP 请求，我们使用了 HTTPie 来安装它。

```py
$ sudo apt install httpie
```

![](img/ccebb7d8f4c4f97a20175e37de3dc387.png)

**步骤 1 :**
迁移项目，创建超级用户和运行服务器

```py
$ python3 manage.py migrate
```

```py
$ python manage.py createsuperuser
```

```py
$ python manage.py runserver 4000
```

**第二步:**
现在，我们需要认证并获取令牌。我们将在终点获得的是
*/api/token/*

```py
$ http post http://127.0.0.1:4000/api/token/ username=spider password=vinayak
```

添加您的用户名和密码

![](img/ca0e1d61a8a037f75f2817fdf44d6ad4.png)

**步骤 3 :**
复制访问令牌并提出请求

```py
$  http http://127.0.0.1:4000/hello/ "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTg3Mjc5NDIxLCJqdGkiOiIzYWMwNDgzOTY3NjE0ZDgxYmFjMjBiMTBjMDlkMmYwOCIsInVzZXJfaWQiOjF9.qtNrUpyPQI8W2K2T22NhcgVZGFTyLN1UL7uqJ0KnF0Y"
```

![](img/c9d097b255b31767bf5cf8ab613dc94b.png)