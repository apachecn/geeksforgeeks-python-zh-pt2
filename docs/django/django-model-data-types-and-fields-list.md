# 姜戈模型数据类型和字段列表

> 原文:[https://www . geesforgeks . org/django-model-data-type-and-field-list/](https://www.geeksforgeeks.org/django-model-data-types-and-fields-list/)

模型最重要的部分，也是模型唯一需要的部分是它定义的数据库字段列表。字段由类属性指定。注意不要选择与模型应用编程接口冲突的字段名，如清除、保存或删除。

**示例:**

```
from django.db import models

class Musician(models.Model):
    first_name = models.CharField(max_length=200)
    last_name = models.CharField(max_length=200)
    instrument = models.CharField(max_length=200)

class Album(models.Model):
    artist = models.ForeignKey(Musician, on_delete=models.CASCADE)
    name = models.CharField(max_length=100)
    release_date = models.DateField()
    num_stars = models.IntegerField()
```

设置一个字段来存储任何类型的数据就像在 C/C++中决定一个数据类型来存储一个特定的整数、字符等。Django 中的字段是存储特定类型数据的数据类型。例如，要存储一个整数，可以使用整数字段。这些字段具有针对特定数据类型的内置验证，也就是说，您不能在 IntegerField 中存储“abc”。同样，对于其他领域。这篇文章围绕着可以在姜戈模型中使用的主要领域。
在开始使用 Django Fields 之前，您应该了解一些关键属性。

### 字段类型

模型中的每个字段都应该是相应字段类的一个实例。Django 使用字段类类型来确定一些事情:

*   列类型，它告诉数据库存储哪种类型的数据(例如 INTEGER、VARCHAR、TEXT)。
*   呈现表单域时使用的默认 HTML 小部件(例如<input type="”text”">、<select>)。</select>
*   最低验证要求，用于 Django 的管理和自动生成的表单。

Django 附带了几十种内置的字段类型，可以用来保存任何类型的数据，从数字到整个 HTML 文件。以下是姜戈使用的所有字段类型的列表。

### 基本模型数据类型和字段列表

<figure class="table">

| 字段名 | 描述 |
| --- | --- |
| [自动场](https://www.geeksforgeeks.org/autofield-django-models/) | 它是一个自动递增的整数域。 |
| [大汽车场](https://www.geeksforgeeks.org/bigautofield-django-models/) | 它是一个 64 位的整数，很像一个自动字段，除了它保证适合从 1 到 9223372036854775807 的数字。 |
| [【big integrieffield】](https://www.geeksforgeeks.org/bigintegerfield-django-models/) | 它是一个 64 位整数，很像一个整数字段，除了它保证适合从-9223372036854775808 到 922372036854775807 的数字。 |
| [BinaryField](https://www.geeksforgeeks.org/binaryfield-django-models/) | 存储原始二进制数据的字段。 |
| [布林栏位](https://www.geeksforgeeks.org/booleanfield-django-models/) | 真/假字段。
该字段的默认表单小部件是 CheckboxInput。 |
| [夏菲尔德](https://www.geeksforgeeks.org/charfield-django-models/) | 存储基于文本的值的字段。 |
| 约会场 | 日期，在 Python 中由 datetime.date 实例表示 |
|   | 它用于日期和时间，在 Python 中由 datetime.datetime 实例表示。 |
| [十进制字段](https://www.geeksforgeeks.org/decimalfield-django-models/) | 它是一个固定精度的十进制数，在 Python 中用十进制实例表示。 |
| 耐久性场 | 用于存储时间段的字段。 |
| [EmailField](https://www.geeksforgeeks.org/emailfield-django-models/) | 它是一个字符域，用于检查该值是否是有效的电子邮件地址。 |
| [文件字段](https://www.geeksforgeeks.org/filefield-django-models/) | 这是一个文件上传字段。 |
| [浮动字段](https://www.geeksforgeeks.org/floatfield-django-models/) | 它是一个浮点数，在 Python 中由一个浮点数实例表示。 |
| [图像场](https://www.geeksforgeeks.org/imagefield-django-models/) | 它继承了 FileField 的所有属性和方法，但也验证了上传的对象是有效的图像。 |
| [整数文件](https://www.geeksforgeeks.org/integerfield-django-models/) | 它是一个整数字段。从-2147483648 到 2147483647 的值在 Django 支持的所有数据库中都是安全的。 |
| [genericispaddresfield](https://www.geeksforgeeks.org/genericipaddressfield-django-models/) | 字符串格式的 IPv4 或 IPv6 地址(例如 192.0.2.30 或 2a02:42fe::4)。 |
| [零乌头田](https://www.geeksforgeeks.org/nullbooleanfield-django-forms/) | 像 BooleanField，但允许空值作为选项之一。 |
| [正积分场](https://www.geeksforgeeks.org/positiveintegerfield-django-models/) | 像整数字段，但必须是正数或零(0)。 |
| [正小积分域](https://www.geeksforgeeks.org/positivesmallintegerfield-django-models/) | 像 PositiveIntegerField，但只允许某个特定点(依赖于数据库)下的值。 |
| [斯拉格菲尔德](https://www.geeksforgeeks.org/slugfield-django-models/) | 鼻涕虫是一个报纸术语。鼻涕虫是某物的简称，只包含字母、数字、下划线或连字符。它们通常用于网址。 |
| [模型整合场](https://www.geeksforgeeks.org/smallintegerfield-django-models/) | 它就像一个 IntegerField，但是只允许在某个(数据库相关的)点下的值。 |
| [TextField](https://www.geeksforgeeks.org/textfield-django-models/) | 一个大的文本字段。此字段的默认表单小部件是文本区域。 |
| [时间域](https://www.geeksforgeeks.org/timefield-django-models/) | 时间，在 Python 中由 datetime.time 实例表示。 |
| 尖叫场 | 网址的字符域，由网址验证器验证。 |
| [UUIDField](https://www.geeksforgeeks.org/uuidfield-django-models/) | 用于存储通用唯一标识符的字段。使用 Python 的 UUID 类。当在 PostgreSQL 上使用时，它存储在 uuid 数据类型中，否则存储在 char(32)中。 |

</figure>

### 关系字段

Django 还定义了一组表示关系的字段。

<figure class="table">

| 字段名 | 描述 |
| --- | --- |
| [外键](https://www.geeksforgeeks.org/python-relational-fields-in-django-models/) | 多对一的关系。需要两个位置参数:与模型相关的类和 on_delete 选项。 |
| [ManyToManyField](https://www.geeksforgeeks.org/python-relational-fields-in-django-models/) | 多对多的关系。需要一个位置参数:与模型相关的类，其工作原理与 ForeignKey 完全相同，包括递归和惰性关系。 |
| [一个字段](https://www.geeksforgeeks.org/python-relational-fields-in-django-models/) | 一对一的关系。从概念上讲，这类似于唯一=真的外键，但是关系的“反向”端将直接返回单个对象。 |

</figure>