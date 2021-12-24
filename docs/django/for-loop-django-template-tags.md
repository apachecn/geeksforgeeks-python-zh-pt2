# 循环的

# -姜戈模板标签

> 原文:[https://www . geesforgeks . org/for-loop-django-template-tags/](https://www.geeksforgeeks.org/for-loop-django-template-tags/)

Django 模板是使用 Django 模板语言标记的文本文档或 Python 字符串。Django 是一个强大的包含电池的框架，为在模板中呈现数据提供了便利。Django 模板不仅允许在视图和模板之间传递数据，还提供了一些有限的编程特性，如变量、循环、注释、扩展等。
本文围绕如何在模板中使用**标记**展开。 **for tag** 循环遍历数组中的每一项，使该项在上下文变量中可用。

**语法:**

```py
{% for i in list %}
{% endfor %}
```

**示例:**

例如，要显示运动员列表中提供的运动员列表:

## 超文本标记语言

```py
<ul>
{% for athlete in athlete_list %}
    <li>{{ athlete.name }}</li>
{% endfor %}
</ul>
```

## for–姜戈模板标签说明

举例说明如何在姜戈模板中使用标签。考虑一个名为 geeksforgeeks 的项目，它有一个名为 geeks 的应用程序。

> 请参考以下文章，查看如何在 Django 中创建项目和应用程序。
> 
> *   [如何利用姜戈的 MVT 创建基础项目？](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
> *   [如何在姜戈创建 App？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

现在创建一个视图，我们将通过它传递上下文字典。

## 蟒蛇 3

```py
# import Http Response from django
from django.shortcuts import render

# create a function
def geeks_view(request):
    # create a dictionary
    context = {
        "data" : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    }
    # return response
    return render(request, "geeks.html", context)
```

创建 url 路径以映射到此视图。在极客/URL . py 中，

## 蟒蛇 3

```py
from django.urls import path

# importing views from views.py
from .views import geeks_view

urlpatterns = [
    path('', geeks_view),
]
```

在 templates/geeks.html 中创建模板，

## 超文本标记语言

```py
{% for i in data %}
    <div class="row">
        {{ i }}
    </div>
{% endfor %}
```

让我们检查一下“/”上显示的内容是否显示在模板中。

![cycle-django-template-tags](img/4c159c992fea46d28c05dbe772916ff2.png)

任何包含在 for 标记之间的内容都将被重复，即循环运行的次数。

#### 高级用法

人们也可以使用变量。例如，如果您有两个模板变量，rowvalue1 和 rowvalue2，您可以像这样在它们的值之间交替:

## 超文本标记语言

```py
{% for o in some_list %}
    <tr class="{% cycle rowvalue1 rowvalue2 %}">
        ...
    </tr>
{% endfor %}
```

#### 高级用法

人们可以通过使用{% for obj in list reversed %}，反向循环一个列表。
如果需要遍历列表，可以将每个子列表中的值解包为单个变量。例如，如果您的上下文包含一个称为点的(x，y)坐标列表，您可以使用以下命令输出点列表:

```py
{% for x, y in points %}
    There is a point at {{ x }}, {{ y }}
{% endfor %}
```

如果您需要访问字典中的项目，这也很有用。例如，如果您的上下文包含字典数据，下面将显示字典的键和值:

```py
{% for key, value in data.items %}
    {{ key }}: {{ value }}
{% endfor %}
```