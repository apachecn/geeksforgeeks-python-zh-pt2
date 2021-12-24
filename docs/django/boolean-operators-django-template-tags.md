# 布尔运算符–姜戈模板标签

> 原文:[https://www . geesforgeks . org/boolean-operators-django-template-tags/](https://www.geeksforgeeks.org/boolean-operators-django-template-tags/)

Django 模板是使用 Django 模板语言标记的文本文档或 Python 字符串。Django 是一个强大的包含电池的框架，为在模板中呈现数据提供了便利。Django 模板不仅允许在视图和模板之间传递数据，还提供了一些有限的编程特性，比如变量、循环、注释、扩展等等。
本文围绕如何在模板中使用**布尔运算符**展开。{% if %}标记计算一个变量，如果该变量为“ **true** ”(即存在，不为空，并且不是假布尔值)，则输出块的内容。人们可以在 Django If 模板标签中使用各种布尔运算符。

**语法:**

```
{% if variable boolean_operator value %}
// statements
{% endif %}
```

**示例:**
如果标签可以使用 and、or 或 or 来测试多个变量或否定给定变量:

## 超文本标记语言

```
{% if athlete_list and coach_list %}
    Both athletes and coaches are available.
{% endif %}

{% if not athlete_list %}
    There are no athletes.
{% endif %}

{% if athlete_list or coach_list %}
    There are some athletes or some coaches.
{% endif %}

{% if not athlete_list or coach_list %}
    There are no athletes or there are some coaches.
{% endif %}

{% if athlete_list and not coach_list %}
    There are some athletes and absolutely no coaches.
{% endif %}
```

可以看到，if 标记可能包含一个或多个{% elif %}子句，以及一个{% else %}子句，如果前面所有条件都失败，该子句将被显示。这些条款是可选的。

## 布尔运算符–姜戈模板标签说明

举例说明如何在姜戈模板中使用布尔运算符。考虑一个名为 geeksforgeeks 的项目，它有一个名为 geeks 的应用程序。

> 请参考以下文章，查看如何在 Django 中创建项目和应用程序。
> 
> *   [如何利用姜戈的 MVT 创建基础项目？](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
> *   [如何在姜戈创建 App？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

现在创建一个视图，我们将通过它传递上下文字典。

## 蟒蛇 3

```
# import Http Response from django
from django.shortcuts import render

# create a function
def geeks_view(request):
    # create a dictionary
    context = {
        "data" : 99,
    }
    # return response
    return render(request, "geeks.html", context)
```

创建 url 路径以映射到此视图。在极客/URL . py 中，

## 蟒蛇 3

```
from django.urls import path

# importing views from views.py
from .views import geeks_view

urlpatterns = [
    path('', geeks_view),
]
```

在 templates/geeks.html 中创建模板，

## 超文本标记语言

```
{% if data == 99 %}
Value in data is : - {{ data }}
{% else %}
Data is empty
{% endif%}
```

让我们检查一下“/”上显示的内容是否显示在模板中。

![if-django-template-tags](img/a68e09472fd5b14e80b367f77d1e00ad.png)

## 布尔运算符

**==运算者**
平等。示例:

```
{% if somevar == "x" %}
  This appears if variable somevar equals the string "x"
{% endif %}
```

**！=运算符**
不等式。示例:

```
{% if somevar != "x" %}
  This appears if variable somevar does not equal the string "x",
  or if somevar is not found in the context
{% endif %}
```

**<符**
不到。示例:

```
{% if somevar < 100 %}
  This appears if variable somevar is less than 100.
{% endif %}
```

**>符**
大过。示例:

```
{% if somevar > 0 %}
  This appears if variable somevar is greater than 0.
{% endif %}
```

**< =运算符**
小于或等于。示例:

```
{% if somevar <= 100 %}
  This appears if variable somevar is less than 100 or equal to 100.
{% endif %}
```

**> =运算符**
大于或等于。示例:

```
{% if somevar >= 1 %}
  This appears if variable somevar is greater than 1 or equal to 1.
{% endif %}
```

**在符**内
所含。许多 Python 容器都支持这个操作符来测试给定值是否在容器中。以下是如何解释 y 中的 x 的一些示例:

```
{% if "bc" in "abcdef" %}
  This appears since "bc" is a substring of "abcdef"
{% endif %}
```

```
{% if "hello" in greetings %}
  If greetings is a list or set, one element of which is the string
  "hello", this will appear.
{% endif %}
```

```
{% if user in users %}
  If users is a QuerySet, this will appear if user is an
  instance that belongs to the QuerySet.
{% endif %}
```

**不在符**内
不在内。这是 in 运算符的否定。
**是符**
的对象身份。测试两个值是否是同一个对象。示例:

```
{% if somevar is True %}
  This appears if and only if somevar is True.
{% endif %}

{% if somevar is None %}
  This appears if somevar is None, or if somevar is not found in the context.
{% endif %}
```

**不算符**
否定对象身份。测试两个值是否不是同一个对象。这是对 is 运算符的否定。示例:

```
{% if somevar is not True %}
  This appears if somevar is not True, or if somevar is not found in the
  context.
{% endif %}

{% if somevar is not None %}
  This appears if and only if somevar is not None.
{% endif %}
```