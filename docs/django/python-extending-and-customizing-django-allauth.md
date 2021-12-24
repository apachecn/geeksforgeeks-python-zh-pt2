# Python |扩展和定制 django-allaus

> 原文:[https://www . geesforgeks . org/python-扩展和定制-django-allauth/](https://www.geeksforgeeks.org/python-extending-and-customizing-django-allauth/)

先决条件:[Django-allaus 设置和配置](https://www.geeksforgeeks.org/python-django-allauth-setup-and-configuration/)

让我们来处理定制 django-allauth 注册表单，干预注册流程以添加定制流程和验证。

**在 django-allaus 中扩展注册表单或添加自定义字段:**

关于 allauth 最常见的查询之一是关于向注册表单中添加附加字段或自定义字段。您可以从 allauth.account.forms 扩展 signingupform 类，只需要创建一个自定义类，将 signingupform 传递给自定义类，定义自定义字段并保存。返回用户对象至关重要，因为它将被传递给其他模块进行验证。您还需要在 settings.py.
中包含一个变量

让我们用一个例子 ***forms.py 来看看这个。**T3】*

## 蟒蛇 3

```py
from allauth.account.forms import SignupForm
from django import forms

class CustomSignupForm(SignupForm):
    first_name = forms.CharField(max_length=30, label='First Name')
    last_name = forms.CharField(max_length=30, label='Last Name')

    def save(self, request):
         user = super(CustomSignupForm, self).save(request)
        user.first_name = self.cleaned_data['first_name']
        user.last_name = self.cleaned_data['last_name']
        user.save()
        return user
```

在上面的代码片段中，CustomSignupForm 扩展了继承 SignupForm 类所有特性的类，并添加了必要的特性。在这里，名为 first _ name 和 last_name 的自定义字段是使用同一类中的注册模块创建和保存的。

上述代码的设置. py 中的 ACCOUNT_FORMS 为

## 蟒蛇 3

```py
ACCOUNT_FORMS = {
'signup': 'YourProject.forms.CustomSignupForm',
}
```

创建的任何其他自定义表单都可以在 ACCOUNT_FORMS 中扩展。该列表在[文档](http://django-allauth.readthedocs.io/en/latest/forms.html#account-forms)中有说明。
同样，*登录用户表单添加邮件表单*等都可以扩展。但是，请记住，当您扩展这些表单并在 settings.py 中链接它们时，不要忘记将原始表单(例如*signingform*)作为参数传递给您的类，有时您可能需要处理自定义验证并返回用户或其他值。请参考[源代码](https://github.com/pennersr/django-allauth/blob/master/allauth/account/forms.py#L362)遵循正确的流程。

**用户干预和自定义验证:**

让我们讨论添加自定义验证和干预用户注册流程。 *DefaultAccountAdapter* 非常有用，确实可以用来解决用户在使用*django*–*allaus*时可能遇到的大部分定制问题。

**示例#1:电子邮件的限制列表**

找到存储和获取受限列表的方法后，当受限电子邮件试图注册时，您可以使用适配器并在注册表单中引发验证错误。扩展*默认帐户适配器*并覆盖*清除电子邮件*方法。在项目目录中创建一个 adapter.py，并扩展默认的适配器类。

## 蟒蛇 3

```py
from allauth.account.adapter import DefaultAccountAdapter
from django.forms import ValidationError

class RestrictEmailAdapter(DefaultAccountAdapter):
    def clean_email(self, email):
        RestrictedList = ['Your restricted list goes here.']
        if email in RestrictedList
            raise ValidationError('You are restricted from registering.\
                                                  Please contact admin.')
        return email
```

最后，将 settings.py 中的帐户适配器指向您的扩展类。

```py
ACCOUNT_ADAPTER='YourProject.adapter.RestrictEmailAdapter'
```

**示例#2:给用户名添加最大长度**

由于 allauth 库中不存在 ACCOUNT_USERNAME_MAX_LENGTH，因此 *DefaultAccountAdaptercan* 用于实现该功能，没有太大的痛苦。扩展*默认帐户适配器类*并覆盖*干净 _ 用户名*方法。在我们的自定义验证之后，您还需要再次引用 *clean_username* 来完成其他内置验证。

上一段最后一句话是使用 *DefaultAccountAdapter* 的关键。您永远不要忘记引用模块的原始模块名来完成其他验证。

## 蟒蛇 3

```py
from allauth.account.adapter import DefaultAccountAdapter
from django.forms import ValidationError

class UsernameMaxAdapter(DefaultAccountAdapter):
    def clean_username(self, username):
        if len(username) > 'Your Max Size':
            raise ValidationError('Please enter a username value\
                                      less than the current one')

        # For other default validations.
        return DefaultAccountAdapter.clean_username(self, username)
```

最后，指向设置中的子类

```py
ACCOUNT_ADAPTER = 'YourProject.adapter.UsernameMaxAdapter'
```

可以参考源代码中的 *adapters.py* [文件](https://github.com/pennersr/django-allauth/blob/master/allauth/account/adapter.py)，扩展其他模块，增加流程或者改变流程。 *populate_username* 、 *clean_password* (可自定义限制常用密码)等模块可以自定义流程和流程，无需重写。
*DefaultAccountAdapter*如果在正确的情况下使用，可以成为干预 allauth 默认流程的有力工具。allauth 自带各种各样的内置设置，这里是。

您也可以从下面参考资料中的链接下载整个源代码。
**参考文献:**
[【姜戈-阿拉鲁斯文档】](http://django-allauth.readthedocs.io/en/latest/)
[示例 1 上的堆栈溢出线程](https://stackoverflow.com/questions/50924482/django-allauth-restrict-registration-to-list-of-emails/50934047#50934047)