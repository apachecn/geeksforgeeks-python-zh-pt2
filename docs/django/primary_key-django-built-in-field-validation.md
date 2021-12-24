# 主键–姜戈内置字段验证

> 原文:[https://www . geesforgeks . org/primary _ key-django-内置字段-验证/](https://www.geeksforgeeks.org/primary_key-django-built-in-field-validation/)

Django 模型中的内置字段验证是所有 Django 字段预定义的默认验证。每个字段都有来自姜戈[验证器](https://docs.djangoproject.com/en/2.2/ref/validators/)的内置验证。还可以添加更多的内置字段验证，以应用或删除特定字段的某些约束。`primary_key=True`将为该表(模型)创建字段**主键**。如果您没有为模型中的任何字段指定 primary_key=True，Django 将自动添加一个自动字段来保存主键，因此您不需要在任何字段上设置 primary_key=True，除非您想要覆盖默认的主键行为。详见[自动主键字段](https://docs.djangoproject.com/en/2.2/topics/db/models/#automatic-primary-key-fields)。

**注** : `primary_key=True`意为`null=False``unique=True`。一个对象上只允许有一个主键。

**语法**

```
field_name = models.Field(primary_key = True)
```

## Django 内置字段验证`primary_key=True`解释

举例说明主键=真。考虑一个名为`geeksforgeeks`的项目，它有一个名为`geeks`的应用程序。

> 请参考以下文章，查看如何在 Django 中创建项目和应用程序。
> 
> *   [如何利用姜戈的 MVT 创建基础项目？](https://www.geeksforgeeks.org/how-to-create-a-basic-project-using-mvt-in-django/)
> *   [如何在姜戈创建 App？](https://www.geeksforgeeks.org/how-to-create-an-app-in-django/)

将以下代码输入**极客** app 的`models.py`文件。我们将使用 IntegerField 对 primary_key 进行实验。

```
from django.db import models
from django.db.models import Model
# Create your models here.

class GeeksModel(Model):
    geeks_field = models.IntegerField(primary_key = True)
```

在 Django 上运行 makemigrations 和 migration 并呈现上述模型之后，让我们尝试使用 Django shell 中的 None 创建一个实例。要启动 Django shell，请输入命令，

```
Python manage.py shell
```

现在让我们尝试使用**无**创建极客模型的实例。

```
# importing required model
from geeks.models import GeeksModel

# creating instance of GeeksModel
s = GeeksModel.objects.create(geeks_field = 12)

# saving current model instance
s.save()
```

让我们检查管理界面，如果模型的实例被创建。
![primary_key=True - Django Built-in Field Validation](img/79baad904a3f793b5e07a71b1ecb1926.png)
因此，primary_key=True 会将该字段修改为该表的 PRIMARY KEY。要了解更多关于主键的信息，请访问此处。

#### 主键=真的高级概念

主键字段是只读的。如果更改现有对象的主键值，然后保存它，将在旧对象的旁边创建一个新对象。

#### 更多内置字段验证

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
| [verbose_name](https://www.geeksforgeeks.org/verbose_name-django-built-in-field-validation/) | 该字段的可读名称。如果没有给出详细名称，Django 将使用字段的属性名称自动创建它，将下划线转换为空格。 |
| [验证器](https://www.geeksforgeeks.org/custom-field-validations-in-django-models/) | 为此字段运行的验证程序列表。更多信息参见[验证器文档](https://docs.djangoproject.com/en/2.2/ref/validators/)。 |
| [独特](https://www.geeksforgeeks.org/uniquetrue-django-built-in-field-validation/) | 如果为真，则该字段在整个表中必须是唯一的。 |