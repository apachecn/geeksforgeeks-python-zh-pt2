# 在姜戈

渲染 HTML 表单(获取&帖子)

> 原文:[https://www . geesforgeks . org/render-html-forms-get-post-in-django/](https://www.geeksforgeeks.org/render-html-forms-get-post-in-django/)

Django 通常被称为“包含电池的框架”，因为它有一个默认设置，可以帮助任何人快速开发网站。说到表单，在 HTML 中，表单是

<form>…</form>

内部元素的集合，允许访问者进行输入文本、选择选项、操作对象或控件等操作，然后将这些信息发送回服务器。基本上，它是一个数据集合，用于处理任何目的，包括将其保存在数据库中或从数据库中获取数据。Django 支持所有类型的 HTML 表单，并使用各种逻辑操作将数据从表单呈现到视图中进行处理。

> 要了解更多关于 HTML 表单的信息，请访问 [HTML |表单标签](https://www.geeksforgeeks.org/html-form-tag/)。

Django 还提供了内置的 **Django 表单**功能，就像 [Django 模型](https://www.geeksforgeeks.org/django-models-set-1/)一样。人们可以在 Django 中创建表单，并使用它们以方便的方式从用户那里获取数据。
首先要熟悉表单中的 [GET 和 POST 请求](https://www.geeksforgeeks.org/get-post-requests-using-python/)。

*   **GET:** 相比之下，GET 将提交的数据打包成一个字符串，并以此组成一个 URL。网址包含必须发送数据的地址，以及数据键和值。如果您在姜戈文档中进行搜索，您可以看到这一点，这将产生一个 https://docs.djangoproject.com/search/?q=forms&版本=1 的网址。
*   **开机自检:**任何可用于更改系统状态的请求(例如，更改数据库的请求)都应该使用开机自检。

### 在姜戈解释中呈现 HTML 表单

使用示例说明**姜戈表格**。考虑一个名为 geeksforgeeks 的项目，它有一个名为 geeks 的应用程序。

> 请参考以下文章，查看如何在 Django 中创建项目和应用程序。
> 
> *   [如何利用姜戈的 MVT 创建基础项目？](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
> *   [如何在姜戈创建 App？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

让我们创建一个简单的 HTML 表单，展示如何从用户输入数据并在视图中使用它。在极客>模板> home.html 中输入以下代码

## 超文本标记语言

```
<form action = "" method = "get">
    <label for="your_name">Your name: </label>
    <input id="your_name" type="text" name="your_name">
    <input type="submit" value="OK">
</form>
```

现在，为了在我们的视图中呈现它，我们需要为极客应用程序修改 urls.py。
在 geeksforgeeks>URL . py 中输入以下代码

## 蟒蛇 3

```
from django.urls import path

# importing views from views..py
from .views import geeks_view

urlpatterns = [
    path('', home_view ),
]
```

现在，让我们转到 home_view，开始检查如何获取数据。在 Django 中，HTML 表单中的所有数据都作为一个称为请求的 JSON 对象进行传输。让我们首先创建一个视图，然后尝试所有方法从表单中获取数据。

## 蟒蛇 3

```
from django.shortcuts import render

# Create your views here.
def home_view(request):

    # logic of view will be implemented here
    return render(request, "home.html")
```