# 文件扩展名验证程序–在姜戈验证文件扩展名

> 原文:[https://www . geesforgeks . org/file extension validator-validate-file-extensions-in-django/](https://www.geeksforgeeks.org/fileextensionvalidator-validate-file-extensions-in-django/)

Django 是一个高级 Python Web 框架，它鼓励快速开发和干净、实用的设计。它由经验丰富的开发人员构建，解决了许多网络开发的麻烦，因此您可以专注于编写应用程序，而无需重新发明轮子。这是免费的开源软件。

### 如何在 Django 中使用 FileExtensionValidator？

为了演示文件扩展验证器的使用，我们将创建一个文件上传器应用程序，在后端验证“pdf”文件。

首先创建新项目。

```py
django-admin startproject fileuploader
```

```py
cd fileuploader
```

然后在项目中创建新的应用程序

```py
python manage.py startapp main
```

然后在**设置中添加你的 INSTALLED_APPS 里面的 app 名称**

![](img/cc260895d9b58daab438c41ac83ed888.png)

**语法:-**

```py
FileExtensionValidator(allowed_extensions, message, code)
```

如果在允许的扩展名中找不到值. name(值为文件)的扩展名，将引发代码为“无效扩展名”的验证错误。扩展与允许的扩展不区分大小写。

**车型. py**

## 蟒蛇 3

```py
from django.core.validators import FileExtensionValidator
class Post(models.Model):
    PDF = models.FileField(null=True, 
                           blank=True, 
                           validators=[FileExtensionValidator( ['pdf'] ) ])
```

**forms.py**

## 蟒蛇 3

```py
from django.forms import ModelForm
from .models import *
from django import forms

class PostForm(ModelForm):
    class Meta:
        model = Post
        fields = __all__
```

**view . py**

## 蟒蛇 3

```py
from django.shortcuts import render,HttpResponse
from .forms import *
# Create your views here.

def home(request):
    form = PostForm()
    return render(request,"main/index.html",{"form":form})
```

**index.html**

## 超文本标记语言

```py
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>
<h2>Welcome To GFG</h2>
<form method="post">
    {% csrf_token %}
      {{form}}
  <button type="submit">Upload</button>
</form>
</body>
</html>
```

用户只能在此文件字段中上传 pdf 文件。否则会抛出异常。此外，总是建议为这样的需求添加客户端验证。本文说明了如何在服务器端验证文件上传。