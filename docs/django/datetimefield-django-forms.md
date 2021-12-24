# 日期时间字段–姜戈表格

> 原文:[https://www.geeksforgeeks.org/datetimefield-django-forms/](https://www.geeksforgeeks.org/datetimefield-django-forms/)

Django 表单中的日期时间字段是一个日期字段，用于从用户那里获取日期和时间的输入。该输入的默认小部件是[日期时间输入](https://docs.djangoproject.com/en/2.2/ref/forms/widgets/#django.forms.DateTimeInput)。它规范化为:一个 Python **datetime.datetime** 对象。它验证给定值是 datetime.datetime、datetime.date 还是以特定日期时间格式格式化的字符串。
**日期时间字段有一个可选参数:**

**input_formats** :-用于尝试将字符串转换为有效的 datetime.datetime 对象的格式列表。

如果未提供 input_formats 参数，默认输入格式为:

```
['%Y-%m-%d %H:%M:%S',    # '2006-10-25 14:30:59'
 '%Y-%m-%d %H:%M',       # '2006-10-25 14:30'
 '%Y-%m-%d',             # '2006-10-25'
 '%m/%d/%Y %H:%M:%S',    # '10/25/2006 14:30:59'
 '%m/%d/%Y %H:%M',       # '10/25/2006 14:30'
 '%m/%d/%Y',             # '10/25/2006'
 '%m/%d/%y %H:%M:%S',    # '10/25/06 14:30:59'
 '%m/%d/%y %H:%M',       # '10/25/06 14:30'
 '%m/%d/%y']             # '10/25/06'

```

**语法**

```
field_name = forms.DateTimeField(**options)
```

## Django 表单日期时间字段解释

使用示例说明日期时间字段。考虑一个名为`geeksforgeeks`的项目，它有一个名为`geeks`的应用程序。

> 请参考以下文章，查看如何在 Django 中创建项目和应用程序。
> 
> *   [如何利用姜戈的 MVT 创建基础项目？](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
> *   [如何在姜戈创建 App？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

将以下代码输入**极客** app 的`forms.py`文件。

```
from django import forms

# creating a form 
class GeeksForm(forms.Form):
    geeks_field = forms.DateTimeField( )
```

将极客应用添加到`INSTALLED_APPS`

```
# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'geeks',
]
```

现在要将这个表单呈现为一个视图，我们需要一个视图和一个映射到该 URL 的 URL。让我们首先在极客应用的 `views.py`中创建一个视图，

```
from django.shortcuts import render
from .forms import GeeksForm

# Create your views here.
def home_view(request):
    context = {}
    context['form'] = GeeksForm()
    return render( request, "home.html", context)
```

这里，我们从 forms.py 导入该特定表单，并在视图中创建它的一个对象，以便它可以在模板中呈现。
现在，要创建一个姜戈表单，你需要创建一个 home.html，在那里你可以按照他们喜欢的方式设计东西。让我们在`home.html`中创建一个表单。

```
<form method = "GET">
    {{ form }}
    <input type = "submit" value = "Submit">
</form>
```

最后，在 urls.py 中映射到此视图的 URL

```
from django.urls import path

# importing views from views..py
from .views import home_view

urlpatterns = [
    path('', home_view ),
]
```

让我们运行服务器并检查实际发生了什么，运行

```
Python manage.py runserver
```

![django-datefield-forms](img/72c5c2b1cf2500c056be18b38305979e.png)

因此，通过将“_”替换为“”，创建了一个 `geeks_field` **日期时间字段**。它是从用户输入日期和时间实例的字段。

## 如何使用 DateTimeField？

日期时间字段用于输入数据库中的日期和时间。可以输入日期和时间、提交的最后日期等。到目前为止，我们已经讨论了如何实现 DateTimeField，但是如何在视图中使用它来执行逻辑部分。为了执行一些逻辑，我们需要将输入到字段中的值输入到 python datetime.datetime 实例中。
在视图中，

```
from django.shortcuts import render
from .forms import GeeksForm

# Create your views here.
def home_view(request):
    context ={}
    form = GeeksForm()
    context['form']= form
    if request.GET:
        temp = request.GET['geeks_field']
        print(type(temp))
    return render(request, "home.html", context)
```

让我们尝试一下除了日期时间字段中的日期之外的其他内容。

![django-datetimefield-forms](img/e84c0e69b16bb8f159c83cb74c8e6f07.png)
所以它只接受日期输入，否则会看到验证错误。现在让我们尝试在字段中输入一个有效的日期。
![django-forms-datefield-validated](img/db019c857e3ca994a3976d3eb1b5a1c5.png)
可以使用相应的请求字典获取日期数据。如果方法是获取，数据将在**请求中可用。获取**如果发布，**请求。相应地开机自检**。在上面的例子中，我们有一个可以用于任何目的的 temp 值。

![django-datetime-forms](img/47e5c2ce840d22069760efaf75e539e2.png)

## 核心字段参数

核心字段参数是为每个字段提供的参数，用于对特定字段应用某种约束或赋予特定特征。例如，向日期时间字段添加参数`required = False`将使用户将其留空。每个字段类构造函数至少接受这些参数。有些字段类采用额外的、特定于字段的参数，但以下参数应始终被接受:

| 字段选项 | 描述 |
| --- | --- |
| [必需](https://www.geeksforgeeks.org/required-django-form-field-validation/) | 默认情况下，每个字段类都假设该值是必需的，因此要使其不是必需的，您需要设置`required=False` |
| 标签 | label 参数允许您为此字段指定“人性化”标签。当字段显示在表单中时使用。 |
| [标签 _ 后缀](https://www.geeksforgeeks.org/label-django-form-field-validation/) | 标签后缀参数允许您在每个字段的基础上覆盖表单的[标签后缀](https://docs.djangoproject.com/en/2.2/ref/forms/fields/#label-suffix)。 |
| 小部件 | widget 参数允许您指定呈现此字段时要使用的 Widget 类。有关更多信息，请参见[小部件](https://docs.djangoproject.com/en/2.2/ref/forms/widgets/)。 |
| [帮助 _ 文字](https://www.geeksforgeeks.org/help_text-django-form-field-validation/) | 帮助文本参数允许您为此字段指定描述性文本。如果提供 help_text，当字段通过方便的表单方法之一呈现时，它将显示在字段旁边。 |
| [错误信息](https://www.geeksforgeeks.org/error_messages-django-form-field-validation/) | error_messages 参数允许您覆盖该字段将引发的默认消息。传入一个字典，其关键字与您想要覆盖的错误消息相匹配。 |
| [验证器](https://www.geeksforgeeks.org/django-form-field-custom-widgets/) | validators 参数允许您为此字段提供一个验证函数列表。 |
| [本地化](http://localize) | localize 参数允许对表单数据输入以及呈现的输出进行本地化。 |
| [禁用](https://www.geeksforgeeks.org/disabled-django-form-field-validation/)。 | 禁用的布尔参数设置为真时，使用禁用的 HTML 属性禁用表单字段，这样用户就无法编辑它。 |

pener" target="_blank " >验证器

validators 参数允许您为此字段提供一个验证函数列表。[本地化](http://localize)localize 参数允许对表单数据输入以及呈现的输出进行本地化。[禁用](https://www.geeksforgeeks.org/disabled-django-form-field-validation/)。禁用的布尔参数设置为真时，使用禁用的 HTML 属性禁用表单字段，这样用户就无法编辑它。