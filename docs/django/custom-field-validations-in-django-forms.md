# 姜戈表单中的自定义字段验证

> 原文:[https://www . geesforgeks . org/custom-field-validations-in-django-forms/](https://www.geeksforgeeks.org/custom-field-validations-in-django-forms/)

本文围绕如何向特定字段添加自定义验证展开。例如，通过指定特定格式向字符域添加电子邮件验证。有多种方法可以实现自定义验证。在本文中，我们将从表单本身展示它，这样您就不需要在其他地方操作它。

### 什么是验证器？

验证器是一个可调用的函数，它接受一个值，如果不满足条件，就会引发验证错误。验证器对于在不同类型的字段之间重用验证逻辑非常有用。

Django 表单的 Django 自定义字段验证说明

使用示例说明验证器。考虑一个名为 geeksforgeeks 的项目，它有一个名为 geeks 的应用程序。

请参考以下文章，查看如何在 Django 中创建项目和应用程序。

*   [How to use MVT in Jiang Ge to create basic projects?](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
*   [How to create an App in Jiang Ge?](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

要在表单域中使用内置验证器，请像这样导入**表单中的验证器。**

 **## 蟒 3

```
from django import forms
from django.core import validators

class StuForm(forms.Form):
  name = forms.CharField(
    validators =[validators.MaxLengthValidator(10)])
```** 

从 Validators 调用内置的 MaxLengthValidators，如果值的长度大于 limit_value，就会引发验证错误。

**如何在 django 中创建我们的自定义验证器？**

因此，我们将创建自己的自定义验证器。

**实施例 1 :-**

我们将创建一个验证器，如果名称不以 s 开头，它将引发一个错误。

## **蟒 3**

 **```
from django import forms

def start_with_s(value):
  if value[0]!='s':
    raise forms.ValidationError("Name should start with s")

class StuForm(forms.Form):
  name = forms.CharField(
    validators =[start_with_s])
```** 

**在验证器中传递函数。**

**我们写一个逻辑，如果一个名字不是以' s '开头，它会引发一个错误，并在函数中换行。**

****实施例 2 :-****

**我们将为移动号码字段**

 **## 创建验证器

```
from django import forms

def mobile_no(value):
  mobile = str(value)
  if len(mobile) != 10:
    raise forms.ValidationError("Mobile Number Should 10 digit")

class StuForm(forms.Form):
  mob = forms.IntegerField(
    validators =[mobile_no])
```** 

**我们编写了一个移动号码验证器逻辑，它会产生一个错误并包装在函数中**