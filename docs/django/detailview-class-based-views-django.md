# 详细视图–基于类的视图姜戈

> 原文:[https://www . geesforgeks . org/detail view-基于类-view-django/](https://www.geeksforgeeks.org/detailview-class-based-views-django/)

详细视图是指显示数据库中某个表实例的视图(逻辑)。我们已经在[详细视图-基于功能的视图姜戈](https://www.geeksforgeeks.org/detail-view-function-based-views-django/)中讨论了详细视图的基础。基于类的视图提供了一种将视图实现为 Python 对象而不是函数的替代方法。它们不会取代基于函数的视图，但与基于函数的视图相比有一定的差异和优势:

*   与特定 HTTP 方法(GET、POST 等)相关的代码的组织。)可以通过单独的方法而不是条件分支来解决。
*   面向对象的技术，如 mixins(多重继承)可以用来将代码分解成可重用的组件。

基于类的视图比基于函数的视图管理起来更简单有效。一个有大量代码行的基于函数的视图可以被转换成只有很少代码行的基于类的视图。这就是面向对象编程产生影响的地方。

## django detailsview–基于类的视图

如何使用实例创建和使用详细视图的说明**。考虑一个名为`geeksforgeeks`的项目，它有一个名为`geeks`的应用程序。**

> 请参考以下文章，查看如何在 Django 中创建项目和应用程序。
> 
> *   [如何利用姜戈的 MVT 创建基础项目？](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
> *   [如何在姜戈创建 App？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

在你有一个项目和一个应用程序后，让我们创建一个模型，我们将通过我们的视图创建实例。在`geeks/models.py`中，

```
# import the standard Django Model
# from built-in library
from django.db import models

# declare a new model with a name "GeeksModel"
class GeeksModel(models.Model):

    # fields of the model
    title = models.CharField(max_length = 200)
    description = models.TextField()

    # renames the instances of the model
    # with their title name
    def __str__(self):
        return self.title
```

创建这个模型后，我们需要运行两个命令来为其创建数据库。

```
Python manage.py makemigrations
Python manage.py migrate

```

现在让我们使用 shell 创建这个模型的一些实例，运行 form bash，

```
Python manage.py shell
```

输入以下命令

```
>>> from geeks.models import GeeksModel
>>> GeeksModel.objects.create(
                       title="title1",
                       description="description1").save()
>>> GeeksModel.objects.create(
                       title="title2",
                       description="description2").save()
>>> GeeksModel.objects.create(
                       title="title2",
                       description="description2").save()

```

现在我们已经为后端做好了一切准备。验证实例是否已从[http://localhost:8000/admin/geeks/geeks model/](http://localhost:8000/admin/geeks/geeksmodel/)创建

![django-listview-check-models-instances](img/dee101808c9cd4f03ff405df85df3887.png)

基于类的视图会自动设置从 A 到 z 的所有内容。只需要指定为哪个模型创建 DetailView，然后基于类的 DetailView 会自动尝试在`app_name/modelname_detail.html`中找到一个模板。在我们的例子中是`geeks/templates/geeks/geeksmodel_detail.html`。让我们创建基于类的视图。在`geeks/views.py`中，

```
from django.views.generic.detail import DetailView

from .models import GeeksModel

class GeeksDetailView(DetailView):
    # specify the model to use
    model = GeeksModel
```

现在创建一个 url 路径来映射视图。在极客/URL . py 中，

```
from django.urls import path

# importing views from views..py
from .views import GeeksDetailView
urlpatterns = [
    # <pk> is identification for id field,
    # slug can also be used
    path('<pk>/', GeeksDetailView.as_view()),
]
```

在`templates/geeks/geeksmodel_detail.html`创建模板，

```
<h1>{{ object.title }}</h1>
<p>{{ object.description }}</p>
```

我们来看看[上有什么 http://localhost:8000/1/](http://localhost:8000/1)
![django-detailview-class-based](img/aa8c1bbfdac686e6ac8f0e84b02d166a.png)

### 在 detailsview 中操作上下文数据

默认情况下，DetailView 将只显示表的字段。如果您想在将上下文数据发送到模板之前对其进行修改或添加一些额外的字段，可以覆盖上下文数据。
在`geeks/views.py`中，

```
from django.views.generic.detail import DetailView

from .models import GeeksModel

class GeeksDetailView(DetailView):
    # specify the model to use
    model = GeeksModel

    # override context data
    def get_context_data(self, *args, **kwargs):
        context = super(GeeksDetailView,
             self).get_context_data(*args, **kwargs)
        # add extra field 
        context["category"] = "MISC"        
        return context
```

在`geeks/templates/geeksmodel_detail.html`中，

```
<h1>{{ object.title }}</h1>
<p>{{ object.description }}</p>
<p>{{ category }}</p>
```

现在检查，如果类别被添加。

![django-detailview-geeksview](img/9984f1e959768a1e093e9693f4f07b36.png)