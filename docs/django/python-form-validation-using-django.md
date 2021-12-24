# Python |使用 django 进行表单验证

> 原文:[https://www . geesforgeks . org/python-表单-验证-使用-django/](https://www.geeksforgeeks.org/python-form-validation-using-django/)

**先决条件** : [姜戈安装](https://www.geeksforgeeks.org/django-introduction-and-installation/) | [姜戈介绍](https://www.geeksforgeeks.org/django-introduction-set-2-creating-a-project/)
姜戈在 MVT 图案上工作。因此需要创建数据模型(或表)。对于每个表，都会创建一个模型类。
假设有一个表单以**用户名**、**性别**、**文本**作为用户输入，任务是验证数据并保存。
在姜戈可以这样做，如下所示:

## 计算机编程语言

```
from django.db import models

# model named Post
class Post(models.Model):
    Male = 'M'
    FeMale = 'F'
    GENDER_CHOICES = (
    (Male, 'Male'),
    (FeMale, 'Female'),
    )

    # define a username filed with bound  max length it can have
    username = models.CharField( max_length = 20, blank = False,
                                 null = False)

    # This is used to write a post
    text = models.TextField(blank = False, null = False)

    # Values for gender are restricted by giving choices
    gender = models.CharField(max_length = 6, choices = GENDER_CHOICES,
                              default = Male)

    time = models.DateTimeField(auto_now_add = True)
```

创建数据模型后，需要将更改反映在数据库中，为此，运行以下命令:

```
python manange.py makemigrations

```

这样做可以编译模型，如果没有发现任何错误，就会在迁移文件夹中创建一个文件。稍后运行下面给出的命令，最终将保存在迁移文件中的更改反映到数据库中。

```
python manage.py migrate

```

现在可以创建表单了。假设用户名长度不应该小于 5，帖子长度应该大于 10。然后，我们用所需的验证规则定义类**后缀**，如下所示:

## 计算机编程语言

```
from django.forms import ModelForm
from django import forms
from formValidationApp.models import *

# define the class of a form
class PostForm(ModelForm):
    class Meta:
        # write the name of models for which the form is made
        model = Post       

        # Custom fields
        fields =["username", "gender", "text"]

    # this function will be used for the validation
    def clean(self):

        # data from the form is fetched using super function
        super(PostForm, self).clean()

        # extract the username and text field from the data
        username = self.cleaned_data.get('username')
        text = self.cleaned_data.get('text')

        # conditions to be met for the username length
        if len(username) < 5:
            self._errors['username'] = self.error_class([
                'Minimum 5 characters required'])
        if len(text) <10:
            self._errors['text'] = self.error_class([
                'Post Should Contain a minimum of 10 characters'])

        # return any errors if found
        return self.cleaned_data
```

到目前为止，已经定义了数据模型和表单类。现在重点将放在如何实际使用上面定义的这些模块上。
首先，通过此命令在本地主机上运行

```
python manage.py runserver

```

在浏览器中打开 **http://localhost:8000/** ，然后在**URL . py**文件中进行搜索，寻找“”路径
T5】URL . py 文件如下:

## 计算机编程语言

```
from django.contrib import admin
from django.urls import path, include
from django.conf.urls import url
from django.shortcuts import HttpResponse
from . import views

urlpatterns = [
    path('', views.home, name ='index'),
]
```

基本上，这将“”url 与功能**相关联，该功能在**view . py**文件中定义。
**view . py 文件** :** 

## **计算机编程语言**

```
from .models import Post
from .forms import PostForm
from .import views
from django.shortcuts import HttpResponse, render, redirect

def home(request):

    # check if the request is post
    if request.method =='POST': 

        # Pass the form data to the form class
        details = PostForm(request.POST)

        # In the 'form' class the clean function
        # is defined, if all the data is correct
        # as per the clean function, it returns true
        if details.is_valid(): 

            # Temporarily make an object to be add some
            # logic into the data if there is such a need
            # before writing to the database  
            post = details.save(commit = False)

            # Finally write the changes into database
            post.save() 

            # redirect it to some another page indicating data
            # was inserted successfully
            return HttpResponse("data submitted successfully")

        else:

            # Redirect back to the same page if the data
            # was invalid
            return render(request, "home.html", {'form':details}) 
    else:

        # If the request is a GET request then,
        # create an empty form object and
        # render it into the page
        form = PostForm(None)  
        return render(request, 'home.html', {'form':form})
```