# Django 模型中的 get_object_or_404 方法

> 原文:[https://www . geesforgeks . org/get _ object _ or _ 404-method-in-django-models/](https://www.geeksforgeeks.org/get_object_or_404-method-in-django-models/)

有些函数每次都很难编码，也很无聊。但是 Django 用户不必担心这一点，因为 Django 有一些很棒的内置功能，可以让我们的工作变得轻松愉快。我们在这里讨论 get_object_or_404()。

### 如何在 Django 项目中使用 get_object_or_404()？

该函数调用给定的模型并从中获取对象，如果该对象或模型不存在，它将引发 404 错误。

#### 示例:

假设我们想从产品模型中获取第三个产品，那么我们可以使用:

## 蟒蛇 3

```py
# import get_object_or_404()
from django.shortcuts import get_object_or_404

# defining view
def product_view(request):
    #
retrieving product (pk is primary key)
    product = get_object_or_404(Products, pk=3)
```

这是 Django 的优势，如果你硬编码，那么你必须写这么多行代码:

## 蟒蛇 3

```py
# import Http404
from django.http import Http404

# defining view
def product_view(request):

    # try except logic
    try:
        product = Products.objects.get(pk=1)
    except Products.DoesNotExist:
        raise Http404("Given query not found....")
```

#### 将 get_object_or_404()与 QuerySet 一起使用:

QuerySet 实例用于在从数据库提取数据时过滤数据。例如，我们想只取鞋，那么我们可以写:

```py
queryset = Products.objects.filter(type='shoes')
get_object_or_404(queryset)
```

我们可以用一行来简化上面的例子:

```py
get_object_or_404(Products, type='shoes') 
```