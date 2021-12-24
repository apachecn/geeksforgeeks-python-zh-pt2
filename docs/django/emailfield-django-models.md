# EmailField–姜戈车型

> 原文:[https://www.geeksforgeeks.org/emailfield-django-models/](https://www.geeksforgeeks.org/emailfield-django-models/)

电子邮件字段是一个字符字段，使用[电子邮件验证器](https://docs.djangoproject.com/en/2.2/ref/validators/#django.core.validators.EmailValidator)检查有效电子邮件地址的值。 **EmailValidator** 通过预定义的正则表达式验证电子邮件，正则表达式检查“@”和“.”在它之后定义的。人们可以通过探索 EmailValidator 本身的选项来改变正则表达式。

**语法**

```
field_name = models.EmailField(max_length=254, **options)
```

**EmailField 有一个额外的必需参数:**

```
EmailField.max_length
```

字段的最大长度(以字符为单位)。`max_length`在数据库级别和 Django 的验证中使用 [MaxLengthValidator](https://docs.djangoproject.com/en/2.2/ref/validators/#django.core.validators.MaxLengthValidator) 强制执行。

## Django 模型电子邮件字段解释

使用示例说明电子邮件字段。考虑一个名为`geeksforgeeks`的项目，它有一个名为`geeks`的应用程序。

> 请参考以下文章，查看如何在 Django 中创建项目和应用程序。
> 
> *   [如何利用姜戈的 MVT 创建基础项目？](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
> *   [如何在姜戈创建 App？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

将以下代码输入**极客** app 的`models.py`文件。

```
from django.db import models
from django.db.models import Model
# Create your models here.

class GeeksModel(Model):
    geeks_field = models.EmailField(max_length = 254)
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

现在当我们从终端运行`makemigrations`命令时，

```
Python manage.py makemigrations
```

将在`geeks`目录中创建一个名为“迁移”的新文件夹，文件名为`0001_initial.py`

```
# Generated by Django 2.2.5 on 2019-09-25 06:00

from django.db import migrations, models

class Migration(migrations.Migration):

    initial = True

    dependencies = [
    ]

    operations = [
        migrations.CreateModel(
            name ='GeeksModel',
            fields =[
                ('id', 
                  models.AutoField(
                  auto_created = True,
                  primary_key = True,
                  serialize = False, 
                  verbose_name ='ID'
                )),
                ('geeks_field', models.EmailField( max_length = 254 )),
            ],
        ),
    ]
```

现在快跑，

```
Python manage.py migrate
```

因此，当您在项目上运行迁移时，会创建一个 `geeks_field` **电子邮件字段**。这是一个在数据库中存储电子邮件地址的字段。

## 如何使用 EmailField？

EmailField 用于在数据库中存储电子邮件地址。可以存储来自任何域的电子邮件 id。让我们尝试在上面创建的模型中存储一个电子邮件 id 实例。

```
# importing the model
# from geeks app
from geeks.models import GeeksModel

# creating a string
d = "abc@gmail.com"

# creating an instance of 
# GeeksModel
geek_object = GeeksModel.objects.create(geeks_field = d)
geek_object.save()
```

现在让我们在管理服务器中检查它。我们已经创建了一个极客模型的实例。
![EmailField django models](img/79baad904a3f793b5e07a71b1ecb1926.png)

## 字段选项

字段选项是为每个字段提供的参数，用于对特定字段应用某些约束或赋予特定特征。例如，向电子邮件字段添加参数`null = True`将使其能够在关系数据库中存储该表的空值。
以下是电子邮件字段可以使用的字段选项和属性。

| 字段选项 | 描述 |
| --- | --- |
| [零](https://www.geeksforgeeks.org/nulltrue-django-built-in-field-validation/) | 如果**为真**，姜戈会在数据库中将空值存储为**空值**。默认为**假**。 |
| [空白](https://www.geeksforgeeks.org/blanktrue-django-built-in-field-validation/) | 如果**为真**，则该字段允许为空。默认为**假**。 |
| 数据库 _ 列 | 用于此字段的数据库列的名称。如果没有给出，Django 将使用字段的名称。 |
| [默认](https://www.geeksforgeeks.org/default-django-built-in-field-validation/) | 该字段的默认值。这可以是一个值或一个可调用对象。如果可调用，它将在每次创建新对象时被调用。 |
| [帮助 _ 文字](https://www.geeksforgeeks.org/help_text-django-built-in-field-validation/) | 要与表单小部件一起显示的额外“帮助”文本。即使您的字段没有在表单上使用，它对文档也很有用。 |
| [主键](https://www.geeksforgeeks.org/primary_key-django-built-in-field-validation/) | 如果为真，则该字段是模型的主键。 |
| [可编辑](https://www.geeksforgeeks.org/editablefalse-django-built-in-field-validation/) | 如果**为假**，该字段将不会显示在管理或任何其他模型表单中。在模型验证期间也会跳过它们。默认为**真**。 |
| [错误信息](https://www.geeksforgeeks.org/error_messages-django-built-in-field-validation/) | error_messages 参数允许您覆盖该字段将引发的默认消息。传入一个字典，其关键字与您想要覆盖的错误消息相匹配。 |
| [帮助 _ 文字](https://www.geeksforgeeks.org/help_text-django-built-in-field-validation/) | 要与表单小部件一起显示的额外“帮助”文本。即使您的字段没有在表单上使用，它对文档也很有用。 |
| [verbose_name](https://www.geeksforgeeks.org/verbose_name-django-built-in-field-validation/) | 该字段的可读名称。如果没有给出详细名称，Django 将使用字段的属性名称自动创建它，将下划线转换为空格。 |
| [验证器](https://www.geeksforgeeks.org/custom-field-validations-in-django-models/) | 为此字段运行的验证程序列表。更多信息参见[验证器文档](https://docs.djangoproject.com/en/2.2/ref/validators/)。 |
| [独特](https://www.geeksforgeeks.org/uniquetrue-django-built-in-field-validation/) | 如果为真，则该字段在整个表中必须是唯一的。 |