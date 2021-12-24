# Django 快捷键:get_list_or_404()

> 原文:[https://www . geesforgeks . org/django-快捷键-get_list_or_404/](https://www.geeksforgeeks.org/django-shortcuts-get_list_or_404/)

有些函数每次都很难编码，也很无聊。但是 Django 用户不必担心这一点，因为 Django 有一些很棒的内置功能，可以让我们的工作变得轻松愉快。让我们在这里讨论 get_list_or_404()。

**get_list_or_404()**

这个函数调用给定的模型并从中获取列表，如果该列表或模型不存在，它将引发 404 错误。

**示例:**

假设我们想从模型中获取文章，那么我们可以使用:

```
# import get_list_or_404()
from django.shortcuts import get_list_or_404

# defining view
def article_view(request):

    # retrieving article from model
    articles = get_list_or_404(Articles)
```

这是 Django 的优势，如果你硬编码它，那么你必须写这么多行代码:

```
# import Http404
from django.http import Http404

# defining view
def article_view(request):

# try except logic
try:
 articles = Articles.objects.all()

except Articles.DoesNotExist:
 raise Http404("Given query not found....")
```