# Uuidfield–姜戈表格

> 原文:[https://www.geeksforgeeks.org/uuidfield-django-forms/](https://www.geeksforgeeks.org/uuidfield-django-forms/)

姜戈表单中的 UUID 字段是一个 UUID 字段，用于用户输入 uuid。该输入的默认小部件是[文本输入](https://docs.djangoproject.com/en/2.2/ref/forms/widgets/#django.forms.TextInput)。它正常化为:一个 UUID 物体。UUID，通用唯一标识符，是一个 python 库，帮助生成 128 位的随机对象作为 ID。要了解更多关于 [UUID 的信息，请访问在 Python 中使用 UUID 生成随机 id](https://www.geeksforgeeks.org/generating-random-ids-using-uuid-python/)。

**语法**

```
field_name = forms.UUIDField(**options)
```

## Django 表单 UUIDField 解释

使用示例说明 UUIDField。考虑一个名为`geeksforgeeks`的项目，它有一个名为`geeks`的应用程序。

> 请参考以下文章，查看如何在 Django 中创建项目和应用程序。
> 
> *   [如何利用姜戈的 MVT 创建基础项目？](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
> *   [如何在姜戈创建 App？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

将以下代码输入**极客** app 的`forms.py`文件。

```
from django import forms

# creating a form 
class GeeksForm(forms.Form):
    geeks_field = forms.UUIDField( )
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

现在要将这个表单渲染成视图，我们需要一个视图和一个映射到 UUID 的 UUID。让我们首先在极客应用的 `views.py`中创建一个视图，

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
<form method = "POST">
    {% csrf_token %}
    {{ form }}
    <input type = "submit" value = "Submit">
</form>
```

最后，一个 UUID 映射到这个视图

```
from django.urls import path

# importing views from views..py
from .views import home_view

UUIDpatterns = [
    path('', home_view ),
]
```

让我们运行服务器并检查实际发生了什么，运行

```
Python manage.py runserver
```

![django-forms-UUIDField](img/3ea488448d74e5087ea3842203a5040a.png)

因此，通过将“_”替换为“”，创建了一个 `geeks_field` **UUIDField** 。

## 如何使用 UUIDField？

UUIDField 用于通过 Django 表单在数据库中输入 UUIDs。可以输入生成的随机数等。到目前为止，我们已经讨论了如何实现 UUIDField，但是如何在视图中使用它来执行逻辑部分。为了执行一些逻辑，我们需要将输入到字段中的值输入到 python 字符串实例中。要查看 UUIDField 的 github 代码，请访问此处

在视图中。py，

```
from django.shortcuts import render
from .forms import GeeksForm

# Create your views here.
def home_view(request):
    context ={}
    form = GeeksForm()
    context['form']= form
    if request.POST:
        temp = request.POST['geeks_field']
        print(temp)
    return render(request, "home.html", context)
```

现在，让我们尝试在该领域中输入其他内容。

![django-forms-UUIDField-12](img/4927df5349bc5b3483837dd66c481aa1.png)

由于需要根据 UUID 进行验证，让我们在字段中输入正确的数据

![django-forms-UUIDField](img/462447066aee896903300677e3fddf14.png)

现在可以使用相应的请求字典来获取这些数据。如果方法是 GET，数据将在**请求中可用。获取**和如果发布，**请求。相应地开机自检**。在上面的例子中，我们有一个可以用于任何目的的 temp 值。

![django-forms-UUIDfield-1](img/223d2cb3a3270247ce58b44000671bae.png)

## 核心字段参数

核心字段参数是为每个字段提供的参数，用于对特定字段应用某种约束或赋予特定特征。例如，向 UUIDField 添加一个参数`required = False`将使用户可以将其留空。每个字段类构造函数至少接受这些参数。有些字段类采用额外的、特定于字段的参数，但以下参数应始终被接受:

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