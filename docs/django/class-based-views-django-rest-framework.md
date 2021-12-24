# 基于类的视图–姜戈休息框架

> 原文:[https://www . geesforgeks . org/class-based-view-django-rest-framework/](https://www.geeksforgeeks.org/class-based-views-django-rest-framework/)

基于类的视图有助于组成可重用的行为。Django REST 框架提供了几个预构建的视图，允许我们重用公共功能并保持代码的干燥。在本节中，我们将深入挖掘 Django REST 框架中不同的基于类的视图。

> 本文假设您已经熟悉了 Django 和 Django REST 框架。
> 
> 结账–
> 
> *   [姜戈教程](https://www.geeksforgeeks.org/django-tutorial/)
> *   [使用 Django Rest 框架](https://www.geeksforgeeks.org/how-to-create-a-basic-api-using-django-rest-framework/)创建一个基本的 API

## APIView

APIView 类为标准列表和详细视图提供了通常需要的行为。有了 APIView 类，我们可以将根视图重写为基于类的视图。它们提供诸如 get()、post()、put()、patch()和 delete()等操作方法，而不是定义处理程序方法。

### 使用 APIView 创建视图

让我们看看如何使用 APIView 创建视图。views.py 文件模块如下:

## 蟒蛇 3

```py
from django.shortcuts import render
from django.http import Http404

from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework import status

from transformers.models import Transformer
from transformers.serializers import TransformerSerializer

class TransformerList(APIView):
    """
    List all Transformers, or create a new Transformer
    """

    def get(self, request, format=None):
        transformers = Transformer.objects.all()
        serializer = TransformerSerializer(transformers, many=True)
        return Response(serializer.data)

    def post(self, request, format=None):
        serializer = TransformerSerializer(data=request.data)
        if serializer.is_valid():
            serializer.save()
            return Response(serializer.data,
                            status=status.HTTP_201_CREATED)
        return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)

class TransformerDetail(APIView):
    """
    Retrieve, update or delete a transformer instance
    """
    def get_object(self, pk):
        # Returns an object instance that should 
        # be used for detail views.
        try:
            return Transformer.objects.get(pk=pk)
        except Transformer.DoesNotExist:
            raise Http404

    def get(self, request, pk, format=None):
        transformer = self.get_object(pk)
        serializer = TransformerSerializer(transformer)
        return Response(serializer.data)

    def put(self, request, pk, format=None):
        transformer = self.get_object(pk)
        serializer = TransformerSerializer(transformer, data=request.data)
        if serializer.is_valid():
            serializer.save()
            return Response(serializer.data)
        return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)

    def patch(self, request, pk, format=None):
        transformer = self.get_object(pk)
        serializer = TransformerSerializer(transformer,
                                           data=request.data,
                                           partial=True)
        if serializer.is_valid():
            serializer.save()
            return Response(serializer.data)
        return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)

    def delete(self, request, pk, format=None):
        transformer = self.get_object(pk)
        transformer.delete()
        return Response(status=status.HTTP_204_NO_CONTENT)
```

代码类似于常规的 Django 视图，但是不同的 HTTP 方法之间有更好的分离。

*   get()方法处理 HTTP GET 请求
*   post()方法处理 HTTP POST 请求
*   put()方法处理 HTTP PUT 请求
*   patch()方法处理 HTTP PATCH 请求
*   delete()方法处理 HTTP DELETE 请求

### 设置网址配置

因为我们使用基于类的视图，所以我们在 urls.py 文件的路径中提到视图的方式略有不同。在 app (transformers)文件夹中创建一个名为 urls.py(如果不存在)的新文件，并添加以下代码

## 蟒蛇 3

```py
from django.urls import path
from rest_framework.urlpatterns import format_suffix_patterns
from transformers import views

urlpatterns = [
    path('transformers/', views.TransformerList.as_view()),
    path('transformers/<int:pk>/', views.TransformerDetail.as_view()),
]

urlpatterns = format_suffix_patterns(urlpatterns)
```

接下来，设置根网址配置。您可以打开 urls.py(设置. py 文件所在的文件夹)并添加以下代码

## 蟒蛇 3

```py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('', include('transformers.urls')),
]
```