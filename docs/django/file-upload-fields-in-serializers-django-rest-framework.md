# 序列化程序中的文件上传字段–姜戈 REST 框架

> 原文:[https://www . geesforgeks . org/file-upload-field-in-serializer-django-rest-framework/](https://www.geeksforgeeks.org/file-upload-fields-in-serializers-django-rest-framework/)

在 Django REST 框架中，序列化的概念就是将数据库数据转换成 javascript 可以使用的数据类型。每个序列化程序都带有一些将要被处理的字段(条目)。例如，如果您有一个名为 Employee 的类，其字段为 Employee_id、Employee_name、is_admin 等。然后，您将需要自动字段、字符字段和 BooleanField 来通过 Django 存储和操作数据。类似地，序列化程序也以相同的原理工作，并且具有用于创建序列化程序的字段。
本文围绕 Django REST 框架中序列化器中的文件上传字段字段展开。有两个主要字段—文件字段和图像字段。

#### 文件字段

FileField 基本上是一种文件表示。它执行 Django 的标准文件字段验证。该字段与[文件字段-姜戈模型](https://www.geeksforgeeks.org/filefield-django-models/)相同。

它有以下参数–

*   **最大长度**–指定文件名的最大长度。
*   **允许空文件**–指定是否允许空文件。
*   **使用 _ url**–如果设置为真，则 URL 字符串值将用于输出表示。如果设置为假，文件名字符串值将用于输出表示。默认为上传文件使用网址设置键的值，除非另有设置，否则为真。

**语法–**

```py
field_name = serializers.FileField(*args, **kwargs)
```

#### ImageField(图像字段)

ImageField 是一种图像表示。它验证上传的文件内容是否与已知的图像格式相匹配。这与[ImageField–Django 表单](https://www.geeksforgeeks.org/imagefield-django-forms/)相同

它有以下参数–

*   **最大长度**–指定文件名的最大长度。
*   **允许空文件**–指定是否允许空文件。
*   **使用 _ url**–如果设置为真，则 URL 字符串值将用于输出表示。如果设置为假，文件名字符串值将用于输出表示。默认为上传文件使用网址设置键的值，除非另有设置，否则为真。

**语法–**

```py
field_name = serializers.ImageField(*args, **kwargs)
```

#### 如何在序列化程序中使用文件上传字段字段？

为了解释文件上传字段的用法，让我们从–[开始使用相同的项目设置如何使用 Django Rest 框架创建一个基本的 API？](https://geeksforgeeks.org/how-to-create-a-basic-api-using-django-rest-framework/)。
现在您的项目中有了一个名为 serializer 的文件，让我们创建一个以 FileField 和 ImageField 为字段的序列化程序。

```py
# import serializer from rest_framework
from rest_framework import serializers

class Geeks(object):
    def __init__(self, files, image):
        self.files = files
        self.image = image

# create a serializer
class GeeksSerializer(serializers.Serializer):
    # intialize fields
    files = serializers.FileField()
    image = serializers.ImageField()
```

现在让我们创建一些对象，并尝试序列化它们，检查它们是否真的在工作，运行–

```py
Python manage.py shell
```

现在，在 shell 中运行以下 python 命令

```py
# import everything from serializers
>>> from apis.serializers import *

# create objects of type Text File and Image
>>> from django.core.files import File
>>> text_file = File(open("test.txt"), 'rb')
>>> image_file = File(open("test.jpeg"), 'rb')

# create a object of type Geeks
>>> obj = Geeks(text_file, image_file)

# serialize the object
>>> serializer = GeeksSerializer(obj)

# print serialized data
>>> serializer.data
{'files': None, 'image': None}

```

这是终端上所有这些操作的输出–

![file-upload-fields-in-serializers-Django-REST-Framework](img/063c380a89e2b8ac6acd5b7289587763.png)

#### 文件上传字段的验证

请注意，这些字段的主要座右铭是传递验证，例如文件字段只验证文件中的数据。让我们检查一下这些验证是否有效–

```py
# Create a dictionary and add invalid values
>>> data = {}
>>> data['files'] = text_file
>>> data['image_file'] = "invalid"

# dictionary created
>>> data
{'files': , 'image_file': 'invalid'}

# deserialize the data
>>> serializer = GeeksSerializer(data=data)

# check if data is valid
>>> serializer.is_valid()
False

# check the errors
>>> serializer.errors
{'image': [ErrorDetail(string='No file was submitted.', code='required')]} 
```

以下是这些命令的输出，清楚地显示图像为无效，文件为有效–

![file-upload-fields-in-serializers](img/e0d1ccacf81b9f5a9fe6f184a5706fab.png)

#### 高级概念

验证是反序列化的一部分，不是序列化的一部分。如前所述，序列化是将已经生成的数据转换成另一种数据类型的过程，因此不需要这些默认的验证。反序列化需要验证，因为数据需要保存到数据库或指定的任何其他操作。所以如果你使用这些字段序列化数据。

## 序列化程序字段中的核心参数

| 争吵 | 描述 |
| --- | --- |
| [只读](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#read_only) | 将该值设置为 True 以确保在序列化表示时使用该字段，但在反序列化期间创建或更新实例时不使用该字段 |
| [只写 _ 条](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#write_only) | 将此设置为“真”，以确保该字段可以在更新或创建实例时使用，但在序列化表示时不包括在内。 |
| [必需](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#required) | 将此设置为 False 还允许在序列化实例时从输出中省略对象属性或字典键。 |
| [默认](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#default) | 如果设置，这将给出默认值，如果未提供输入值，该默认值将用于该字段。 |
| [允许 _ 空](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#allow_null) | 通常情况下，如果将“无”传递给序列化程序字段，将会引发错误。如果“无”应被视为有效值，则将此关键字参数设置为“真”。 |
| [来源](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#source) | 将用于填充字段的属性的名称。 |
| [验证器](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#validators) | 应该应用于输入字段输入的验证函数列表，这些函数要么引发验证错误，要么简单地返回。 |
| [错误信息](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#error_messages) | 错误信息的错误代码字典。 |
| 标签 | 一个短文本字符串，可用作 HTML 表单字段或其他描述性元素中的字段名称。 |
| [帮助 _ 文字](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#help_text) | 一个文本字符串，可用作 HTML 表单字段或其他描述性元素中字段的描述。 |
| [初始](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#initial) | 应该用于预先填充 HTML 表单字段值的值。 |