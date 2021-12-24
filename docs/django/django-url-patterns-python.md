# 姜戈网址模式| Python

> 原文:[https://www.geeksforgeeks.org/django-url-patterns-python/](https://www.geeksforgeeks.org/django-url-patterns-python/)

**Prerequisites:** [Views in Django](https://www.geeksforgeeks.org/views-in-django-python/)

在 Django 中，视图是 Python 函数，它以一个 URL 请求为参数，返回一个 HTTP 响应或抛出一个类似 404 的异常。每个视图都需要映射到相应的网址模式。这是通过一个名为 URL 配置的 Python 模块来完成的

让项目名为 myProject。用作 URLConf 的 Python 模块是`**myProject/settings.py**`中`ROOT_URLCONF`的值。默认设置为`'myProject.urls'`。每个 URLConf 模块必须包含一个变量`urlpatterns`，它是一组要与请求的 URL 匹配的 URL 模式。将依次检查这些模式，直到找到第一个匹配。然后调用对应于第一个匹配的视图。如果没有匹配的网址模式，Django 会调用一个适当的错误处理视图。

**包括其他 URLConf 模块**
在姜戈的每个应用都有一个 URLConf 模块是一个很好的做法。该模块需要包含在根 URLConf 模块中，如下所示:

```py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('books.urls')),
]
```

这告诉姜戈在文件`**books/urls.py**`中搜索网址模式。

**网址模式**

以下是书籍/URL 的示例代码。py:

```py
from django.urls import path
from . import views

urlpatterns = [
    path('books/<int:pk>/', views.book_detail),
    path('books/<str:genre>/', views.books_by_genre),
    path('books/', views.book_index), 
]
```

例如，

*   到/图书/犯罪/的网址请求将与第二个网址模式匹配。因此，Django 将调用函数`views.books_by_genre(request, genre = "crime")`。
*   类似地，一个网址请求/books/25/将匹配第一个网址模式，Django 将调用函数`views.book_detail(request, pk =25)`。

这里，`int`和`str`是路径转换器，分别捕获整数和字符串值。

**路径转换器:**
以下路径转换器类型在姜戈可用

*   **int**–匹配零或任何正整数。
*   **字符串**–匹配任何非空字符串，不包括路径分隔符('/')。
*   **slug**–匹配任何 slug 字符串，即由字母、数字、连字符和下划线组成的字符串。
*   **路径**–匹配任何非空字符串，包括路径分隔符('/')
*   **uuid**–匹配 uuid(通用唯一标识符)。